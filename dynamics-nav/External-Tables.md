---
title: "External Tables"
ms.custom: na
ms.date: 15/05/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
---
# External Tables 

This article describes how to integrate an external table into a [!INCLUDE[navnow](includes/navnow_md.md)] application.

> [!NOTE]
> The concepts discussed in the article provide the basis for integrating [!INCLUDE[navnow](includes/navnow_md.md)] with external products like [!INCLUDE[crm](includes/crm_md.md)], Microsoft Graph, and Exchange. Microsoft Graph and Exchange integration is done for you. For [!INCLUDE[crm](includes/crm_md.md)] integration, we provide several tools and features that make the integration easier than doing it all manually as described in this article. For more information, see [Integrating Dynamics 365 for Sales in Dynamics NAV](Integrating-Dynamics-CRM-in-Dynamics-NAV.md).

## About external tables

An *external table* is a table that resides outside of the [!INCLUDE[navnow](includes/navnow_md.md)] database, in another database either on SQL Server or Azure SQL Database. The external database can be hosted on the same database server as the [!INCLUDE[navnow](includes/navnow_md.md)] database or a different server. 

### How this differs from linked objects
You might be familiar with the *linked objects* feature in [!INCLUDE[navnow](includes/navnow_md.md)], which offers another way of integrating an external SQL table (see [Using Linked Objects](Using-Linked-Objects.md)). The difference with the method described in this article is that the table connections are controlled at runtime. This provides a more dynamic table relationship than creating table definitions from SQL Server objects using linked objects. 

### What the guidelines for using an external table are
In general, to use an external table, you perform the following tasks:

-   Create a table in [!INCLUDE[navnow](includes/navnow_md.md)] that represents the external table. This table is referred to as the *companion* table.

-   Add application code that establishes a connection between the two tables. Connecting a [!INCLUDE[navnow](includes/navnow_md.md)] table to an external table is primarily controlled from the application code and involves three operations:

    -   Registering the table connection to the external database.
    -   Setting the table connection.
    -   Unregistering the table connection. 

-  Create a page that uses the companion table as its source to enable client users can view, modify, create, and delete records in the table. This task is optional.

At runtime, data from the external table is read into the [!INCLUDE[navnow](includes/navnow_md.md)] record instance. The data is not persisted in the local database; it is only in memory.

When records from the external table are instantiated, the connection is set on them. Any changes that client users make to records are pushed back to the external table. 


### How commits on external tables are handled 
[!INCLUDE[navnow](includes/navnow_md.md)] commits on all connections at the same time. This includes the application database connection (in a multitenant deployment), tenant database connection, and any registered external table connections. If there are open transactions on more than one database, then commits will occur one database at a time, starting with the application database. If a commit fails, the current transaction and all remaining transactions will be rolled back; any transactions that were successfully committed will not be rolled back.

## Creating a [!INCLUDE[navnow](includes/navnow_md.md)] companion table
You create a companion table in [!INCLUDE[navnow](includes/navnow_md.md)] like any other table, except there are several properties that you set to couple the companion table with the external table. Structurally, the companion table reflects that of the external table, although you do not have to include all columns of the external table. For each column in the external table that you want accessible from [!INCLUDE[navnow](includes/navnow_md.md)], you add a field with a compatible data type to the companion table.

On the table-level, you must set the following properties:

|Property|Value|
|--------|-----|
|[TableType](tabletype-property.md)|**ExternalSQL**|
|[ExternalName](externalname-property.md)|The name of the table in the external database.|
|[ExternalSchema](externalschema-property.md)|The schema of the table in the external database.|

On the field-level, you set the following properties:

|Property|Value|
|--------|-----|
|[Name](name-property.md)|The name to assign the field. You can use the same name as the column in the external table or use a different name. If you use a different name, you must set the field's **ExternalName** property.|
|[DataType](data-type-property.md)|The data type that matches the column in the external table. For more information, see [Representation of SQL Data Types](Identifiers--Data-Types--and-Data-Formats.md#SQLDataType). |
|[Length](datalength-property.md) |The length the matches the column in the external table.|
|[ExternalName](externalname-property.md)|The name of the column in the external table. This property is required only if the field's **Name** property differs from the column name in the external table.|

## Registering an external table connection
The first step when using an external table is to register a connection to the database that contains the external table. This makes the connection available for use. There are two ways to do this. One way is to call the REGISTERTABLECONNECTION function from code. The other way is to use the [New-NAVTableConnection cmdlet](https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.management/new-navtableconnection) from the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)]. 

-  Using the REGISTERTABLECONNECTION function provides a more dynamic and customizable way of registering a table connection. When registered by the REGISTERTABLECONNECTION function, the connection is registered for the current client session only and will clear once the session has ended.

-  Using the New-NAVTableConnection cmdlet provides a static and global way of registering a table connection. The registered table connection is stored to the application database, which makes the connection available always.

### Using the REGISTERTABLECONNECTION function
The REGISTERTABLECONNECTION function can be called from anywhere in your application code. For example, you might want to register the connection when the page that uses the table is opened or when the company is initialized (see the [examples](#Examples) section to see these in code). 

The REGISTERTABLECONNECTION function has the following syntax:

```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, <TableConnectionName>, <ConnectionString>) 
```
where:

-   `<TableConnectionName>` - specifies a name for identifying and managing the connection. 
-   `<ConnectionString>` - specifies the connection string, or data source name (DSN), to the database that contains the external table. The connection string specifies information about the external database, like the database server (and instance), the database name, and the login credentials.

The following sections include REGISTERTABLECONNECTION function calls for some typical connection strings. The brackets `<>` indicate information that you substitute with values specific to your environment.

#### SQL Server database with SQL authentication

With SQL Server authentication, the SQL Server stores the user name and password for the login. The server is identified by the its name or IP address, and the database instance: 

```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, '<TableConnectionName>', 'Data Source=<DatabaseServer>\<DatabaseServerInstance>;Initial Catalog=<DatabaseName>;User ID=<username>;Password=<password>');  
```  
For example:
``` 
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;User ID=admin;Password=P@ssword123!');
``` 

#### SQL Server database with Windows authentication

Windows authentication uses the login credentials of the current user to make the connection to SQL Server, where SQL Server validates the uses against Windows Active Directory. The server is identified by the its name, or IP address, and the database instance:  

```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, '<TableConnectionName>', 'Data Source=<DatabaseServer>\<DatabaseServerInstance>;Initial Catalog=<DatabaseName>;Integrated Security=SSPI;');  
```  
For example:

``` 
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;Integrated Security=SSPI;');
``` 

#### Azure SQL Database

With a database in Azure SQL database, you can get the connection string from the Azure Portal. The following syntax is simplified for illustration purposes. The actual connection string may vary:

```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, '<TableConnectionName>', 'Server=<server>.database.windows.net;Database=<azuredatabase>;User ID=<username>;Password=<password>'); 
```  

For example:

``` 
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyAzureTableConnection1', 'Server=myazureserver.database.windows.net;Initial Catalog=MyAzureDatabase;User ID=admin;Password=P@ssword123!;');
``` 

### Using the New-NAVTableConnection cmdlet
The New-NAVTableConnection cmdlet stores the external table connection information to a table in the [!INCLUDE[navnow](includes/navnow_md.md)] database. Information about table connections is stored in an application table. Unlike using the REGISTERTABLECONNECTION function, you do not have to provide the connection string to the external database; only the database information. The actual connection string will be automatically determined. 

To register a table connection, start the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)], and then run the following command:

```
New-NAVTableConnection -ServerInstance <NAVServerInstance> -ConnectionType ExternalSQL -ConnectionId '<TableConnectionName>' -DatabaseServer '<DatabaseServer>\<DatabaseInstance>' -DatabaseName '<ExternalDatabaseName>'
```
For example:

```
New-NAVTableConnection -ServerInstance DynamicsNAV -ConnectionType ExternalSQL -ConnectionId 'MyTableConnection1' -DatabaseServer 'MyDatabaseServer\NAVDEMO' -DatabaseName 'MyExternalDatabase'
```

> [!TIP]
> To get information about registered table connections, use the [Get-NAVTableConnection cmdlet](https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.management/new-navtableconnection).


## Setting an external table connection 
After the code for registering the connection is in place, the next step is to add code to establish the connection to the external table. This is done by adding a call to the SETDEFAULTTABLECONNECTION function. 

The SETDEFAULTTABLECONNECTION function has the following syntax:

```  
SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, '<TableConnectionName>');  
```  
`<TableConnectionName>` is the name that is assigned to the external table connection by the REGISTERTABLECONNECTION function.

For example, together with the REGISTERTABLECONNECTION function, your code might look like this:

```
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;Integrated Security=SSPI;');
SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyTableConnection1');  
```  

## Unregistering an external table connection  
When done using an external table connection or if the connection must be refreshed, it can be unregistered by using either the UNREGISTERTABLECONNECTION function or the [Remove-NAVTableConnection cmdlet](https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.management/remove-navtableconnection). 

-   If a table connection was registered by the UNREGISTERTABLECONNECTION function, use the UNREGISTERTABLECONNECTION function. 

-   If a table connection was registered by the New-NAVTableConnection cmdlet, use the Remove-NAVTableConnection cmdlet. 

### Using the UNREGISTERTABLECONNECTION function
When a table connection is registered by the REGISTERTABLECONNECTION function, it remains registered until the current client session has ended. If there is application code that tries to register a table connection that is currently registered, a runtime error occurs. To avoid this, call the UNREGISTERTABLECONNECTION function before calling the REGISTERTABLECONNECTION function.

> [!NOTE]
> When UNREGISTERTABLECONNECTION is called, the current transaction will be rolled back.  

The UNREGISTERTABLECONNECTION function has the following syntax:

```  
UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, '<TableConnectionName>');
``` 

For example, together with the REGISTERTABLECONNECTION and SETDEFAULTTABLECONNECTION functions, your code might look like this: 

```
UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1');
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;Integrated Security=SSPI;');
SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyTableConnection1');  
``` 

> [!TIP]
> You can use the [HASTABLECONNECTION](HASTABLECONNECTION-function--database-.md) to verify whether a connection to an external database exists.

### Using the Remove-NAVTableConnection cmdlet

The Remove-NAVTableConnection cmdlet deletes a registered table connection from the application database. To unregister a table connection, start the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)], and then run the following command:

```
Remove-NAVTableConnection -ServerInstance <NAVServerInstance> -ConnectionType ExternalSQL -ConnectionId '<TableConnectionName>'
```

For example:

```
Remove-NAVTableConnection -ServerInstance DynamicsNAV -ConnectionType ExternalSQL -ConnectionId 'MyTableConnection1'
```

> [!TIP]
> To get information about registered table connections, use the [Get-NAVTableConnection](https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.management/get-navtableconnection) cmdlet.

## <a name="Examples"></a>Example 1
This example integrates a simple table from an external SQL Server database. It adds a companion table in [!INCLUDE[navnow](includes/navnow_md.md)] for the external table and a page for viewing and modifying data in the client. The registration and setting of the external table connection is controlled from the page code and occurs when the page opens. 

> [!TIP]
> For more examples of how you can use the functions related to external tables, see codeunits 5330 and 5331 in the standard version of [!INCLUDE[navnow](includes/navnow_md.md)].  

### Prerequisites
This example assumes that the following external database and table already exist. 

**External database properties**

The external database has the following properties:

|Property|Value|
|--------|-----|
|Database server name|MyDatabaseServer|
|Database server instance|NAVDEMO|
|Authentication|Windows|
|Database name|MyExternalDatabase|
|Schema| dbo|

**External table**

The table has the name **MyExternalTable** and includes the following columns:

|Column Name|Data Type|
|-----------|---------|
|ID|int|
|Name|nchar(30)|
|Date| datetime| 

> [!TIP]
> Use SQL Server Management Studio to create, modify, and view the external table.

### Create the [!INCLUDE[navnow_md](includes/navnow_md.md)] companion table
1. Using the [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)], create a table object and set the following properties:

    |Property|Value|
    |--------|-----|
    |[TableType](tabletype-property.md)|**ExternalSQL**||
    |[ExternalName](externalname-property.md)|MyExternalTable||
    |[ExternalSchema](externalschema-property.md)|dbo|
 
2. Add the three fields to the table that map to the columns in the external table:

    |Name|Data Type|Length|ExternalName|
    |----|---------|------|------------|
    |No.|integer||ID|
    |Name|text|30||
    |Date|datetime|||

    In this example, you want the `No.` field to map to the `ID` field in the external database. Because the names are different, you mustset the `ExternalName`property of the `No.` field to the column name in the external table, which in this case is `ID`. 
3. Save the table and give it the ID **50101** and name **MySampleTable**.


### Create a page for viewing data of the companion table from the client
1. Create a list-type page object that has the table **MySampleTable** as its source and includes the three fields of the table. Give the page the ID **50name **MySamplePage**.
2. Add the following code to `OnInit` page trigger to register and set the connection to the external table:

    ```
    IF HASTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1') THEN
        UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyTableConnection1');
    REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalTable;Integrated Security=SSPI;');
    SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyTableConnection1');
    ```

The code for the new page will look like this:

```
OBJECT Page 50101 MySamplePage
{
  OBJECT-PROPERTIES
  {
    Date=;
    Time=;
    Modified=Yes;
    Version List=;
  }
  PROPERTIES
  {
    SourceTable=Table50101;
    PageType=List;
    OnInit=BEGIN
        IF HASTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1') THEN
            UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyTableConnection1');
        REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalTable;Integrated Security=SSPI;');
        SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyTableConnection1');
    END;

  }
  CONTROLS
  {
    { 1   ;0   ;Container ;
                ContainerType=ContentArea }

    { 2   ;1   ;Group     ;
                Name=Group;
                GroupType=Repeater }

    { 3   ;2   ;Field     ;
                SourceExpr="No."; }

    { 4   ;2   ;Field     ;
                SourceExpr=Name; }

    { 5   ;2   ;Field     ;
                SourceExpr=Date }

  }
  CODE
  {

    BEGIN
    END.
  }
}

```

### Test the external table connection

Run page **MySamplePage** to open it in the client. Add and modify records in the list, and then view the external table **MyExternalTable** in SQL Server Management Studio to verify the changes. 

## Example 2
This example slightly modifies the previous example. Instead of registering and setting the external table connection when the **MySamplePage** opens, this example registers and sets the external table connection when the company opens. This is done by subscribing to the `OnAfterCompanyOpen()` event that is published by the codeunit **1 ApplicationManagement**. 

1. Using the [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)], create a codeunit object that has the name **RegisterExternalConnections**.

2. Add a local function named **InitializeExternalConnections** and set the following properties to make the function an event subscriber that subscribes to the `OnAfterCompanyOpen()` event:

    |Property|Value|
    |--------|-----|
    |[Event](event-property.md)|**Subscriber**|
    |[EventPublisherObject](EventPublisherObject-property.md)|Codeunit ApplicationManagement|
    |[EventFunction](EventFunction-property.md) |OnAfterCompanyOpen|

3. On the `InitializeExternalConnections` function, add the following code to register and set the connection to the external database and table:

    ```
    REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;Integrated Security=SSPI;');
    SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyTableConnection1');
    ```

    The codeunit code will look like this:

    ```
    OBJECT Codeunit 50101 RegisterExternalConnections
    {
        OBJECT-PROPERTIES
        {
            Date=;
            Time=1;
            Modified=Yes;
            Version List=;
        }
        PROPERTIES
        {
            OnRun=BEGIN
                END;

        }
        CODE
        {

            [EventSubscriber(Codeunit,1,OnAfterCompanyOpen)]
            LOCAL PROCEDURE InitializeTableConnections@1();
            BEGIN
                REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;Integrated Security=SSPI;');
                SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyTableConnection1');
            END;

            BEGIN
            END.
        }
    } 
    ```
4. In the **MySamplePage** page, remove the code on the `OnInit` page trigger that registers and sets the connection to the external table.

## See Also  
 [TableType Property](TableType-Property.md)   
 [Overview of Tables](Overview-of-Tables.md)   
 [Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)

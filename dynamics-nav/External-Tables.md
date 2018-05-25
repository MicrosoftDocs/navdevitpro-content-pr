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
<!--An *external table* is a table that is contained in a database other than [!INCLUDE[navnow](includes/navnow_md.md)] database. The database can be on the same server [!INCLUDE[navnow](includes/navnow_md.md)] database or a different server. This article describes how to integrate an external table that is hosted in SQL Server or Azure SQL Database into [!INCLUDE[navnow](includes/navnow_md.md)].-->

<!-- This article describes how to integrate a table from an external SQL Server or Azure SQL Database database into [!INCLUDE[navnow](includes/navnow_md.md)].--> 

This article describes how to integrate an external table into a [!INCLUDE[navnow](includes/navnow_md.md)] application. An *external table* is a table that resides outside of the [!INCLUDE[navnow](includes/navnow_md.md)] database, in another database either on SQL Server or Azure SQL Database. The external database can be hosted on the same database server as the [!INCLUDE[navnow](includes/navnow_md.md)] database or a different server. 

> [!NOTE]
> The concepts discussed in the article provide the basis for integrating [!INCLUDE[navnow](includes/navnow_md.md)] with external products like [!INCLUDE[crm](includes/crm_md.md)], Microsoft Graph, and Exchange. Microsoft Graph and Exchange integration done autometically for you. For [!INCLUDE[crm](includes/crm_md.md)] integration, we recommend other our tools and functionality made available that make the integration easier. For more information, see [Integrating Dynamics 365 for Sales in Dynamics NAV](Integrating-Dynamics-CRM-in-Dynamics-NAV.md).

## Overview

In short, to use an external table, you create a companion table in [!INCLUDE[navnow](includes/navnow_md.md)] that represents the external table. Then, you add application code that establishes connection between the two tables. At runtime, data from the external table is read into the [!INCLUDE[navnow](includes/navnow_md.md)] table. By creating a page that uses the companion table as its source, client users can view, modify, create, and delete records in the table, and the changes are pushed back to the external table. 

<!-- Creating or modifying records in the [!INCLUDE[navnow](includes/navnow_md.md)] table will be reflected in the external table, and vice versa.-->

Because the connection is controlled at runtime, this method provides a more dynamic table relationship than creating table definitions from SQL Server objects using linked objects.

### Commits
[!INCLUDE[navnow](includes/navnow_md.md)] commits on all connections at the same time, such as at the same time for the tenant database connection and the application database connection in multitenant deployments. When an external connection is registered, it is joined into this so that any errors will rollback on all connections in use.  
  
When records from external tables are instantiated, the connection is set on them. 


 

<!--
You can create tables in [!INCLUDE[navnow](includes/navnow_md.md)] that represent tables in external products, such as [!INCLUDE[crm](includes/crm_md.md)] and SQL Server. This is a more dynamic table relationship than creating table definitions from SQL Server objects using linked objects, because the connection to the external table can be changed at runtime. In [!INCLUDE[navnowlong](includes/navnowlong_md.md)] you can define two types of external tables: [!INCLUDE[crm](includes/crm_md.md)] tables and **SQL Server** tables. You create an external table by specifying the type of in the TableType property.  


> [!IMPORTANT]  
>  We advise against creating tables of type CRM manually. Instead, use the integration mapping functionality. For more information, see [Integration Concepts and Terminology](Dynamics-CRM-Integration-Concepts-and-Terminology.md).  

-->

## Creating a [!INCLUDE[navnow](includes/navnow_md.md)] companion table

You create a companion table in [!INCLUDE[navnow](includes/navnow_md.md)] like any other table, except there are several properities that you set to couple the companion table with the external table. Structurally, the companion table reflects that of the external table, although you do not have to include all columns of the external table. For each column in the external table that you want accessible from [!INCLUDE[navnow](includes/navnow_md.md)], you add a field with a compatible data type to the companion table.

On the table-level, you must set the following properties:

|Property|Value|
|--------|-----|
|[TableType](tabletype-property.md)|**ExternalSQL**|
|[ExternalName](externalname-property.md)|The name of the table in the external database.|
|[ExternalSchema](externalschema-property.md)|The database schema of the external database.|

On the field-level, you set the following properties:

|Property|Value|
|--------|-----|
|[Name](name-property.md)|The name to assign the field. You can use the same name as the column in the external table or use a diffent name. If you use a different name, you must set the ExternalName property of the field.|
|[DataType](data-type-property.md)|The data type that matches the column in the SQL Server or Azure SQL Database table. For more information, see [Representation of SQL Data Types](Identifiers--Data-Types--and-Data-Formats.md#SQLDataType) |
|[Length](datalength-property.md) |The length the matches the column in the SQL Server or Azure SQL Database table|
|[ExternalName](externalname-property.md)|The name of the table in the external database. This property is required only if the field name in the [!INCLUDE[navnow](includes/navnow_md.md)] table differs from the column name in the external table.|

## Connecting to an external table  
<!-- Connecting a [!INCLUDE[navnow](includes/navnow_md.md)] table to an external table is controlled from the application code by three C/AL functions: REGISTERTABLECONNECTION,  SETDEFAULTTABLECONNECTION, and UNREGISTERTABLECONNECTION.-->

Connecting a [!INCLUDE[navnow](includes/navnow_md.md)] table to an external table is primarily controlled from the application code and involves three operations: registering the table connection, setting the table connection, and unregistering the table connection. 

### Registering a table connection
The first step when connecting an external table is to register the table connection for use. There are two ways to do this. One way is to call the REGISTERTABLECONNECTION function from code. The other way is to use the New-NAVTableConnection cmdlet from the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)]. 

-  Using the REGISTERTABLECONNECTION function provides a more dynamic and customizable way of registering a table connection. When registered by the REGISTERTABLECONNECTION function, the connection is registered for the current client session only and will clear once the session has ended.

-  Using the New-NAVTableConnection cmdlet provides a more static and global way of registering a table connection. The registered table connection is stored to the application database, which makes it available at all times.

#### Using the REGISTERTABLECONNECTION function
The REGISTERTABLECONNECTION function can be called from anywhere in your application code. For example, you might want to register the connection when the company is initialized, as in the example that follows, or when the page that uses the external table opens.

The REGISTERTABLECONNECTION function has the following syntax:

```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, <TableConnectionName>, <ConnectionString>) 
```
where:

-   `<TableConnectionName>` - specifies a name for the connection. You will use this name to identify and manage the connection. 
-   `<ConnectionString>` - specifies the connection string, or data source name (DSN), to the database that contains the external table. The connection string specifies information about the external databse, like the database server (and instance), the database name, and the login credentials.

The following sections include REGISTERTABLECONNECTION function calls for some typical connection strings. The brackets `<>` indicate information that you substitute with values specific to your enviromnent.

**SQL Server database with SQL authentication**

With SQL Server authentication, the SQL Server stores the user name and password for the login. The server is identified by the its name or IP address, and the database instance: 

```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, '<TableConnectionName>', 'Data Source=<DatabaseServer>\<DatabaseServerInstance>;Initial Catalog=<DatabaseName>;User ID=<username>;Password=<password>');  
```  
For example:
``` 
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;User ID=admin;Password=P@ssword123!');
``` 

**SQL Server database with trusted authentication**

Trusted authentication uses the login credentials of the current user to make the connection to SQL Server, where SQL Server validates the uses against Windows Active Directory. The server is identified by the its name, or IP address, and the database instance:  

```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, '<TableConnectionName>', 'Data Source=<DatabaseServer>\<DatabaseServerInstance>;Initial Catalog=<DatabaseName>;Integrated Security=SSPI;');  
```  
For example:

``` 
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;Integrated Security=SSPI;');
``` 

**Azure SQL Database database**

With a database in Azure SQL database, you can get the connection string from the Azure Portal. The following syntax is simplified for illustration purposes. The actual connection string may vary:

```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, '<TableConnectionName>', 'Server=<server>.database.windows.net;Database=<azuredatabase>;User ID=<username>;Password=<password>'); 
```  

For example:

``` 
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'CronusTableConnection', 'Server=cronus.database.windows.net;Initial Catalog=fabrikamdb;User ID=admin;Password=P@ssword123!;');
``` 

#### Using the New-NAVTableConnection cmdlet
The New-NAVTableConnection cmdlet adds table connection information to a table in the [!INCLUDE[navnow](includes/navnow_md.md)] database that is connected to a specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance. In a multitenant deployment, information about the connections is added to a table in the application database. Unlike using the REGISTERTABLECONNECTION function, you do not have to provide the connection string to the external database; only the database information. The actual connection string will be automatically determined. 

To register a table connection, start the [!INCLUDE[nav_shell_md](includes/nav_shell_md.md)], and then run the following command:

```
New-NAVTableConnection -ServerInstance <NAVServerInstance> -ConnectionType ExternalSQL -ConnectionId '<TableConnectionName>' -DatabaseServer '<DatabaseServer>\<DatabaseInstance>' -DatabaseName '<ExternalDatabaseName>'
```

> [!TIP]
> To get information about registered table connections, use the [Get-NAVTableConnection](https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.management/new-navtableconnection) cmdlet.


<!-- I did not need this command. it actually failed  

The actual table connection settings can also be managed using the following new [!INCLUDE[wps_2](includes/wps_2_md.md)] cmdlets. In multitenant deployments, information about the connections is added to a table in the application database. 

|Cmdlet Name|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|-----------------|---------------------------------------|  
|New-NAVTableConnection|Creates a connection to an external table.|  
|Remove-NAVTableConnection|Removes an established connection to an external table.|  
|Get-NAVTableConnection|Gets information about connections to external tables.|  
 

 If you know that your integration with the external product will be managed by [!INCLUDE[wps_2](includes/wps_2_md.md)] cmdlets, your code must call **RegisterTableConnection** without the actual connection string as shown in the following code example. 

  
```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'ExternalDb1');  
```  

instead I used this command. But I could not get it to work on AzureDB--> 



<!-- 
In this scenario, you can write a function that generates a connection string based on the current configuration. 
-->


### Setting an external table connection 
After the code for registering the connection is in place, the next step is to add code to establish the connection to the external table. This is done by adding a call to the SETDEFAULTTABLECONNECTION function on the registered table connection's name. 

The SETDEFAULTTABLECONNECTION function has the following syntax:

```  
SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, '<ExternalConnectionName>');  
```  

For example, together with the REGISTERTABLECONNECTION function, your code might look like this:

```
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;Integrated Security=SSPI;');
SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyTableConnection1');  
```  

### Unregister a table connection  
When done using an external table that is connected to a given source you can , issue the following command. When UNREGISTERTABLECONNECTION is called, the current transaction will be rolled back.  
  
```  
UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, '<MyExternalConnectionName>');
``` 

For example, together with the REGISTERTABLECONNECTION and SETDEFAULTTABLECONNECTION functions, your code might look like this: 

```
UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1');
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;Integrated Security=SSPI;');
SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyTableConnection1');  
```  
## Example
This example integrates a simple table from an external SQL Server database. In addition to a companion table in [!INCLUDE[navnow](includes/navnow_md.md)], a page is also added for entering data into the table from the client.

> [!TIP]
> For more examples of how you can use these functions, see codeunits 5330 and 5331 in the standard version of [!INCLUDE[navnow](includes/navnow_md.md)].  

This example uses the following external database and table. 

**External database properties**

The external database has the following properties:
|Property|Value|
|--------|-----|
|Database server name|MyDatabaseServer|
|Database server instance|NAVDEMO|
|Authentication|Windows|
|Database name|MyExternalDatabase|
|Schema| dbo||

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
1. Using the [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)], create a table object that has the name **MyNavTable**, and set the following properties:

    |Property|Value|
    |--------|-----|
    |[TableType](tabletype-property.md)|**ExternalSQL**||
    |[ExternalName](externalname-property.md)|MyExternalTable||
    |[ExternalSchema](externalschema-property.md)|dbo|
 
2. Add the three fields to the table that map to the columns in the external table:

    |Name|Data Type|Length|
    |----|---------|------|
    |No.|integer||
    |Name|text|30|
    |Date|datetime||

    In this example, you want the `No.` field to map to the `ID` field in the external database. Because the names are different, you have to set the `ExternalName`property of the `No.` field name to the column name in the external table, in this case, `ID`. 

The code for the new table will be similar to the following:

```
OBJECT Table 5001 MyNavTable
{
    OBJECT-PROPERTIES
    {
        Date=;
        Time=;
        Modified=;
     Version List=;
    }
    PROPERTIES
    {
        TableType=ExternalSQL;
        ExternalName=MyExternalTable;
        ExternalSchema=dbo;
    }
    FIELDS
    {
        { 1   ;   ;No.                 ;Integer       ;ExternalName=ID;
                                                   DataClassification=ToBeClassified }
        { 2   ;   ;Name                ;Text30        ;DataClassification=ToBeClassified }
        { 3   ;   ;Date                ;DateTime      ;DataClassification=ToBeClassified }
    }
    KEYS
    {
        {    ;No.                                     ;Clustered=Yes }
    }
    FIELDGROUPS
    {
    }
    CODE
    {

        BEGIN
        END.
    }
}
```
### Create a page for modifying data of the companion table from the client

Using the [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)], create a list page object that has the companion table **MyNavTable** as its source and includes the three fields of the table. Give the page the name **MyNavPage**.

The page code will be similar to the following:

```
OBJECT Page 5001 MyNavPage
{
    OBJECT-PROPERTIES
    {
        Date=;
        Time=;
        Modified=;
        Version List=;
    }
    PROPERTIES
    {
        SourceTable=Table5006;
        PageType=List;
    }
    CONTROLS
    {
        { 1   ;0   ;Container ;
                ContainerType=ContentArea }

        { 2   ;1   ;Group     ;
                Name=Group;
                GroupType=Repeater }

        { 3   ;2   ;Field     ;
                SourceExpr="No." }

        { 4   ;2   ;Field     ;
                SourceExpr=Name }

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

### Add code to register and set connection to the external table

For this example, you want to register the connection to the database when the company opens.  To do this, you create a codeunit that subscribes to the `OnAfterCompanyOpen()` event that is published by the codeunit **1 ApplicationManagement**.

1. Using the [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)], create a codeunit object that has the name **RegistesterExternalConnections**.

2. Add a local function named **InitializeExternalConnections** and set the following properties to make the function a event subscriber that subscribes to the `OnAfterCompanyOpen()` event:

    |Property|Value|
    |--------|-----|
    |[Event](event-property.md)|**Subscriber**|
    |[EventPublisherObject](EventPublisherObject-property.md)|Codeunit ApplicationManagement|
    |[EventFunction](EventFunction-property.md) |OnAfterCompanyOpen|

3. On the `InitializeExternalConnections` function, add the following code to register and set the connection to the external database and table:

    ```
    If UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1');
    REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;Integrated Security=SSPI;');
    SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyTableConnection1');
    ```
    In this example, you assign the connection the name `MyTableConnection1`.

    The UNREGISTERTABLECONNECTION function call is used to clear the previous connection. 


The codeunit code will be similar to the following:

```
OBJECT Codeunit 5001 RegsisterExternalConnections
{
    OBJECT-PROPERTIES
    {
        Date=;
        Time=1;
        Modified=;
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
            UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1');
            REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyTableConnection1', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;Integrated Security=SSPI;');
            SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyTableConnection1');
        END;

        BEGIN
        END.
    }
} 
```

### Test the external table connection

Run page **MyNavPage** to open it in the client. Add and modify records in the list, and then view the external table **MyExternalTable** in SQL Server Management Studio to verify the changes. 

## See Also  
 [TableType Property](TableType-Property.md)   
 [Overview of Tables](Overview-of-Tables.md)   
 [Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)
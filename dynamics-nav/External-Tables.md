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
An *external table* is a table that is contained in database other than [!INCLUDE[navnow](includes/navnow_md.md)] database. This article describes how to integrate an external table from SQL Server or Azure SQL Database into [!INCLUDE[navnow](includes/navnow_md.md)].<!-- This article describes how to integrate a table from an external SQL Server or Azure SQL Database database into [!INCLUDE[navnow](includes/navnow_md.md)].--> To do this, you create a companion table in [!INCLUDE[navnow](includes/navnow_md.md)] that represents the external table. Then, you add application code that establishes connection between the two tables at runtime. At runtime, data from the external table is read into the [!INCLUDE[navnow](includes/navnow_md.md)] table. Records can be modified and  created, and the changes are pushed back to the external table. 

 Creating or modifying records in the [!INCLUDE[navnow](includes/navnow_md.md)] table will be reflected in the external table, and vice versa. Because the connection is controlled at runtime, this provides a more dynamic table relationship than creating table definitions from SQL Server objects using linked objects.

> [!NOTE]
> The concepts discussed in the article provide the basis for integrating [!INCLUDE[navnow](includes/navnow_md.md)] with external products like [!INCLUDE[crm](includes/crm_md.md)], Microsoft Graph, and Exchange. Microsoft Graph and Exchange integration done internally for you. For [!INCLUDE[crm](includes/crm_md.md)], there are other tools and functionality available that make the integration easier than manually implementing the concepts discussed in this article. For more information, see [Integrating Dynamics 365 for Sales in Dynamics NAV](Integrating-Dynamics-CRM-in-Dynamics-NAV.md). 

<!--
You can create tables in [!INCLUDE[navnow](includes/navnow_md.md)] that represent tables in external products, such as [!INCLUDE[crm](includes/crm_md.md)] and SQL Server. This is a more dynamic table relationship than creating table definitions from SQL Server objects using linked objects, because the connection to the external table can be changed at runtime. In [!INCLUDE[navnowlong](includes/navnowlong_md.md)] you can define two types of external tables: [!INCLUDE[crm](includes/crm_md.md)] tables and **SQL Server** tables. You create an external table by specifying the type of in the TableType property.  


> [!IMPORTANT]  
>  We advise against creating tables of type CRM manually. Instead, use the integration mapping functionality. For more information, see [Integration Concepts and Terminology](Dynamics-CRM-Integration-Concepts-and-Terminology.md).  

-->

## Creating a [!INCLUDE[navnow](includes/navnow_md.md)] companion table

You create a companion table in [!INCLUDE[navnow](includes/navnow_md.md)] like any other table, except there are several properities that you set to couple the table with the external table. Structurally, the companion table reflects that of the external table. For each column in the external table that you want accessible from [!INCLUDE[navnow](includes/navnow_md.md)], you add a field that has a compatible data type in the companion table.

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
|[DataType](data-type-property.md)|The data type that matches the column in the SQL Server or Azure SQL Database table. |
|[Length](datalength-property.md) |The length the matches the column in the SQL Server or Azure SQL Database table|
|[ExternalName](externalname-property.md)|The name of the table in the external database. This property is required only if the field name in the [!INCLUDE[navnow](includes/navnow_md.md)] table differs from the column name in in the SQL Server or Azure SQL Database table.|

## Connecting to an external table  
Connecting a [!INCLUDE[navnow](includes/navnow_md.md)] table to an external table is controlled from the application code by three C/AL functions: REGISTERTABLECONNECTION,  SETDEFAULTTABLECONNECTION, and UNREGISTERTABLECONNECTION.

### Register a connection to the database by using a REGISTERTABLECONNECTION function call

The first step when connecting an external table is to call the REGISTERTABLECONNECTION function to register the connection to the external database. The REGISTERTABLECONNECTION function has the following syntax:

```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, <Name>, <ConnectionString>) 
```
where:

-   `<Name>` specifies a name to assign the the connection. You will use this name when set the connection. 
-   `<Connection>`specifies the connection string to the database that contains the external table. The connection string specifies information about the external databse, like the database server (and instance), the database name, and the login credentials.

The following are REGISTERTABLECONNECTION function calls for some typical connection strings:

**SQL Server database with SQL authentication**

With SQL Server authentication, the SQL Server stores the username and password for the login. The server is identified by the its name, or IP address, and the database instance: 

```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, '<MyExternalConnection1>', 'Data Source=<mydbserver\mydbinstance>;Initial Catalog=<myexternaldb1>;User ID=<sqlusername>;Password=<p@ssword>');  
```  

**SQL Server database with trusted authentication**

Trusted authentication uses the login credentials of the current user to make the connection to SQL Server, where SQL Server validates the uses against Windows Active Directory. The server is identified by the its name, or IP address, and the database instance:  

```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, '<MyExternalConnection1>', 'Data Source=<mydbserver\mydbinstance>;Initial Catalog=<myexternaldb1>;Integrated Security=SSPI;');  
```  

**Azure SQL Database database**

With a database in Azure SQL database, you can get the connection string from the Azure Portal:

```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, '<MyExternalConnection1>', 'Server=<myserver.database.windows.net;Database=<MyAzureDatabase>;User ID=<adminusername>;Password=<p@ssword>'); 
```  

[!INCLUDE[navnow](includes/navnow_md.md)] commits on all connections at the same time, such as at the same time for the tenant database connection and the application database connection in multitenant deployments. When an external connection is registered, it is joined into this so that any errors will rollback on all connections in use.  
  
When records from external tables are instantiated, the connection is set on them. 

### Connect to the external table by using a SETDEFAULTTABLECONNECTION function call
After the database connection is registered, the next step is to establish the connection to the table in the external database. To set the current table connection, issue the following C/AL command so that different instances can use different connections. 
```  
SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyExternalConnection1');  
```  

### Unregister a connection to the external database by using a UNREGISTERTABLECONNECTION function call  
When done using a set of tables that are connected to a given source, issue the following command. For tables of type ExternalSQL, when **UnregisterTableConnection** is called, the current transaction will be rolled back.  
  
```  
UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'ExternalDb1');  
```  

### Unregister to the external table by using a SETDEFAULTTABLECONNECTION function call  
To see examples of how you can use these functions, see codeunits 5330 and 5331 in the standard version of [!INCLUDE[navnow](includes/navnow_md.md)].  
  
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
  
In this scenario, you can write a function that generates a connection string based on the current configuration. 


## Example
This example integrates a simple table from an external SQL Server database. In addition to a companion table in [!INCLUDE[navnow](includes/navnow_md.md)], a page is also added for entering data into the table from the client.

This example uses the following external database and table. 

**External database properties**

The external database has the follwoing properties:
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
    |No.|integer|
    Name|nchar(30)|
    |Date| datetime| 

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

### Add code to register and set connetion to the external table

For this example, you want to register the connection to the database when the company opens.  To do this, you create a codeunit that subscribes to the `OnAfterCompanyOpen()` event that is published by the codeunit **1 ApplicationManagement**.

1. Using the [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)], create a codeunit  object that has the name **RegistesterExternalConnections**.

2. Add a local function named **InitializeExternalConnections** and set the following properties to make the function a event subscriber that subscribes to the `OnAfterCompanyOpen()` event:

    |Property|Value|
    |--------|-----|
    |[Event](event-property.md)|**Subscriber**|
    |[EventPublisherObject](EventPublisherObject-property.md)|Codeunit ApplicationManagement|
    |[EventFunction](EventFunction-property.md) |OnAfterCompanyOpen|

3. On the `InitializeExternalConnections` function, add the following code to register and set the connection to the external database and table:

    ```
    UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyExternalTableConnection');
    REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyExternalTableConnection', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;Integrated Security=SSPI;');
    SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyExternalTableConnection');
    ```
    In this example, you assign the connection the name `MyExternalTableConnection`.

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
            UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyExternalTableConnection');
            REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'MyExternalTableConnection', 'Data Source=MyDatabaseServer\NAVDEMO;Initial Catalog=MyExternalDatabase;Integrated Security=SSPI;');
            SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL,'MyExternalTableConnection');
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
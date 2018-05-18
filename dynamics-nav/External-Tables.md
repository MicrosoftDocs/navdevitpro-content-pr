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
This article describes how to integrate and synchronize data from an external SQL Server or Azure SQL Database table with the [!INCLUDE[navnow](includes/navnow_md.md)] database. In short, you do this by creating a companion table in [!INCLUDE[navnow](includes/navnow_md.md)] that represents the external table, and then establishing a connection between the two tables at runtime. Creating or modifying records in the [!INCLUDE[navnow](includes/navnow_md.md)] table will be reflected in the external table, and vice versa. Because the connection is controlled at runtime, this provides a more dynamic table relationship than creating table definitions from SQL Server objects using linked objects.

> [!NOTE]
> The concepts discussed in the article provide the basis for the integration of [!INCLUDE[navnow](includes/navnow_md.md)] with external products like [!INCLUDE[crm](includes/crm_md.md)], Microsoft Graph, and Exchange.

<!--
You can create tables in [!INCLUDE[navnow](includes/navnow_md.md)] that represent tables in external products, such as [!INCLUDE[crm](includes/crm_md.md)] and SQL Server. This is a more dynamic table relationship than creating table definitions from SQL Server objects using linked objects, because the connection to the external table can be changed at runtime. In [!INCLUDE[navnowlong](includes/navnowlong_md.md)] you can define two types of external tables: [!INCLUDE[crm](includes/crm_md.md)] tables and **SQL Server** tables. You create an external table by specifying the type of in the TableType property.  


> [!IMPORTANT]  
>  We advise against creating tables of type CRM manually. Instead, use the integration mapping functionality. For more information, see [Integration Concepts and Terminology](Dynamics-CRM-Integration-Concepts-and-Terminology.md).  

-->

## Creating [!INCLUDE[navnow](includes/navnow_md.md)] companion tables

You create a companion table in [!INCLUDE[navnow](includes/navnow_md.md)] like any other table. You add a field in the companion table for each column in the external table that you want accessible from [!INCLUDE[navnow](includes/navnow_md.md)], making sure the data types are compatible.

On the table level, you must set the following properties:

|Property|Value|
|--------|-----|-------|
|[TableType](tabletype-property)|**ExternalSQL**||
|[ExternalName](externalname-property.md)|The name of the table in the external database.|
|[ExternalSchema](externalschema-property.md)|The database schema of the external database.|

For fields, you set the following properties:

|Property|Value|Example|
|--------|-----|-------|
|[Name](name-property.md)|The name to assign the field. You can use the same name as the column in the external table or use a diffent name. If you use a different name, then you must set the ExternalName property of the field.|
|[DataType](data-type-property.md)|The data type that matches the column in the SQL Server or Azure SQL Database table. |
|[Length](datalength-property.md) |The length the matches the column in the SQL Server or Azure SQL Database table|
|[ExternalName](externalname-property.md)|The name of the table in the external database. This property is required only if the field name in the [!INCLUDE[navnow](includes/navnow_md.md)] table differs from the column name in in the SQL Server or Azure SQL Database table.||


## Connecting to External Tables  
[!INCLUDE[navnow](includes/navnow_md.md)] commits on all connections at the same time, such as at the same time for the tenant database connection and the application database connection in multitenant deployments. When an external connection is registered, it is joined into this so that any errors will rollback on all connections in use.  
  
To use an external table in your code, you must first register one or more connections to the external database as shown in the following code example.  
  
```  
REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'ExternalDb1', 'Data Source=ProdServer1;Initial Catalog=ProdDb1;User ID=sqladmin;Password=p@ssword');  
```  
  
When records from external tables are instantiated, the connection is set on them. To set the current table connection, issue the following C/AL command so that different instances can use different connections.  
  
```  
SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'ExternalDb1');  
```  
  
When done using a set of tables that are connected to a given source, issue the following command. For tables of type ExternalSQL, when **UnregisterTableConnection** is called, the current transaction will be rolled back.  
  
```  
UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'ExternalDb1');  
```  
  
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
This example integrates a simple table in an SQL Server database with [!INCLUDE[navnow](includes/navnow_md.md)].   
1. In SQL Server or Azure SQL Database, identify or create a table that includes the columns that you want.
2. In [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)], create a table object, and set the following properties:

    |Property|Value|Example|
    |--------|-----|-------|
    |[TableType](tabletype-property)|**ExternalSQL**||
    |[ExternalName](externalname-property.md)|The name of the table in the external database.||
    |[ExternalSchema](externalschema-property.md)|The database schema of the external database.|dbo|

3. Add a field in the [!INCLUDE[navnow](includes/navnow_md.md)] table for each column in the SQL Server or Azure SQL Database table. Set the following properties
for each field:
    |Property|Value|Example|
    |--------|-----|-------|
    |[Name](name-property.md)|**ExternalSQL**|The name to assign the field. You can use the same name as the column in the SQL Server or Azure SQL Database table or use a diffent names. If you use a different name, then you must set the [ExternalName](externalname-property.md) property of the field.||
    |[DataType](data-type-property.md)|The data type that matches the column in the SQL Server or Azure SQL Database table. ||
    |[Length](datalength-property.md) |The length the matches the column in the SQL Server or Azure SQL Database table||
    |[ExternalName](externalname-property.md)|The name of the table in the external database. This property is required only if the field name in the [!INCLUDE[navnow](includes/navnow_md.md)] table differs from the column name in in the SQL Server or Azure SQL Database table.||

## Connect the [!INCLUDE[navnow](includes/navnow_md.md)] table to the external table

1. Register the connection to the external table.

    Use the REGISTERTABLECONNECTION function to register the connection to external database. The function has the following syntax:

    ```  
    REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, <Name>, <Connection>)  
    ```   
    Replace `<Name>` with a name that you want to assign the the connection. You will use this name when set the connection. 
    Replace `<Connection>` with the connection string for the database that contains the external table. 

    ```  
    REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::ExternalSQL, 'ExternalDb1', 'Data Source=ProdServer1;Initial Catalog=ProdDb1;User ID=sqladmin;Password=p@ssword');  
    ```
 
  
## See Also  
 [TableType Property](TableType-Property.md)   
 [Overview of Tables](Overview-of-Tables.md)   
 [Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)
---
title: Shared Schema
description: Provides and over view of the the shared schema data model.
ms.date: 10/16/2017
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
author: jswymer
---
# Shared Schema
Shared schema is a data model that shares database resources among tenants and companies of tenants. Shared schema optimizes the reuse of resources, such as execution plans, memory, and database connections, which can help lower operation and administration costs.

## Overview
To understand shared schema, it can help to first look at the conventional [!INCLUDE[navnow_md](includes/navnow_md.md)] data model, which is referred to as the *separate schema* model.

### Separate schema 
By default, [!INCLUDE[navnow_md](includes/navnow_md.md)] uses a *separate schema* data model. This data model has these important characteristics: 

-  Each company has their own set of tables for storing business entity data, such as the Item, Customer, and Invoice tables (see figure 1). 
-  In a multitenant deployment, each tenant has its own database. 

 ![Separate schema](media/separateschema2companies.png "Separate schema")
**Figure 1: Companies in the separate schema data model**

### Shared schema

The shared schema data model has these characteristics: 

-  Companies in the database share tables for storing data. There is one set of business entity data tables, such as Item and Customer, for all companies and all tenants (see figure 2). 
-  In a multitenant deployment, a database can be shared by more than one tenant. Information about the tenants, including its companies, is stored is shared tables. 

For example, there is an Item table for Company 1 and an Item table for Company 2. With the shared database schema model, a single entity table contains the data for all companies. For example, the Item table now contains data for both Company A and Company B.
The shared database schema model is especially designed for a multitenant deployment. In a multitenant deployment, instead of having one single database containing entity data and application data, you now have an application database and one or more tenant databases. The application database contains tables that describe your application. A tenant database contains tables for storing business data for multiple tenants, where each tenant can hold one or more companies. In a tenant database, an entity table will contain data for all tenants and their companies. For example, let’s say you have a tenant database that includes Tenant1 (with companies C and D) and Tenant2 (with companies E and F). This is illustrated in figure 1.
 
Figure 1: Tenant database with two tenants that have two companies 
The Item table would then contain data for companies C, D, E and F, as illustrated in figure 2.
 
Figure 2: Item table with two tenants and four companies
You should note that the concept of a tenant database has changed with Microsoft Dynamics NAV CTP1. Previously, there was one database for each tenant. Now, a database contains multiple tenants. This change has introduced several new PowerShell cmdlets for managing the databases and tenant, such as Mount-NAVTenantDatabase, Sync-NAVTenantDatabase, and more.
Prerequisites
The walkthrough guide in this blog requires the following:
•	Dynamics NAV TENERIFE CTP 1. You can download the installation media here (link pending).
•	A working Dynamics NAV deployment environment, complete with: 
o	Dynamics NAV Server
o	Dynamics NAV database
o	Dynamics NAV Web Server components
o	Dynamics NAV Administration Shell
o	Dynamics NAV Development Environment (optional)
•	SQL Server Management Studio (optional)
Enable Shared Database Schema Model
Follow these steps to enable the shared database schema in a Dynamics NAV server instance (single-tenant or multitenant).
1.	Run the Dynamics NAV Administration Shell as an administrator.
2.	At the command prompt, run the following command:
Set-NAVServerConfiguration -ServerInstance <server_instance_name> -KeyName FeatureSwitchOverrides -KeyValue SharedDb 
Replace <server_instance_name> with the name of your Dynamics NAV Server instance. For example, if your Dynamics NAV Server instance is named DynamicsNAV100, then the command will be:
Set-NAVServerConfiguration -ServerInstance DynamicsNAV100 -KeyName FeatureSwitchOverrides -KeyValue SharedDb
3.	Restart the Dynamics NAV Server instance:
Set-NAVServerInstance -ServerInstance <server_instance_name> -Restart
4.	Run the following command to synchronize the tenant database schema.
For a non-multitenant server instance:
Sync-NAVTenant -ServerInstance <server_instance_name> 
For a multitenant server instance:
Sync-NAVTenant -ServerInstance <server_instance_name> -Id <tenantId>
Replace <tenantId> with the ID of one of your tenants
The synchronization process for upgrading tables to the shared database schema begins as displayed in the console.
5.	To verify that the changes were successful, do the following: 
o	Open SQL Server Management Studio, and inspect the tables in the database. Entity tables, such as “Item”, should now have a new column called CompanyID.
o	Run the Dynamics Web Client, and test that the application works as before.
o	Open the Dynamics NAV Environment, and take a look around.
Migrate to Multitenancy
After enabling the shared schema data model, follow these steps if want to try it out in a multitenant deployment. This is not needed if you just want to test the new data model. The steps separate your database into an application database and tenant database, configure the Dynamics NAV Server instance, and add a tenant.
Note: For examples of the commands used in these steps, see the Sample PowerShell Commands section that follows.
1.	Stop the Dynamics NAV Server instance.
Set-NAVServerInstance -ServerInstance <server_instance_name> -ServiceAccount <domain\username> -Stop 
The ServiceAccount parameter is only required if the server instance is run using a domain account instead of the NT AUTHORITY\NETWORK SERVICE account. This pertains to all steps.
2.	Export the application objects from the database to a new application database:
Export-NAVApplication –DatabaseServer <database_server_name> –DatabaseInstance <database_instance_name> –DatabaseName <original_database_name> –DestinationDatabaseName <new_application_database_name> -ServiceAccount <domain\username>
3.	Remove the application object from the original database. This now becomes the tenant database.
Remove-NAVApplication –DatabaseServer <database_server_name> –DatabaseInstance <database_instance_name> –DatabaseName <original_database_name>
4.	Configure the Dynamics NAV Server instance to be in multitenant mode:
Set-NAVServerConfiguration -ServerInstance <server_instance_name> -KeyName multitenant -KeyValue true
5.	Configure the Dynamics NAV Server instance to use the new application database:
Set-NAVServerConfiguration -ServerInstance <server_instance_name> -KeyName DatabaseName -KeyValue <new_application_database_name>
6.	Start the Dynamics NAV Server instance:
Set-NAVServerInstance -ServerInstance <server_instance_name> -ServiceAccount <nav_server_account> -start
7.	Mount the tenant database to server instance:
Mount-NAVTenantDatabase -ServerInstance <server_instance_name> -DatabaseName <database_name> -Id <tenant_db_ID>
8.	Mount a new tenant to the tenant database and server instance:
Mount-NAVTenant -ServerInstance <server_instance_name> -TenantDatabaseId <tenant_database_Id> -Id <tenant_Id> -OverwriteTenantIdInDatabase
9.	Synchronize the tenant schema to the application database:
Sync-NAVTenant -ServerInstance <server_instance_name> -Id <tenant_Id>
Synchronization process starts.
You should now have a multitenant deployment. To verify, open the Dynamics NAV Web client. You will have to add the tenant=<tenant_Id> parameter in the URL to point to the new tenant, where <tenant_Id> is ID that you set in step 8. For example: http://localhost:8080/DynamicsNAV100/WebClient/default.aspx?tenant=mytenanta.
Sample PowerShell Commands
The following are sample commands for the previous guide, based on the CRONUS International Ltd. demonstration database on a local computer. You can run these commands individually in the Dynamics NAV Administration Shell or as a script in Windows PowerShell (ISE).
The commands do the following:
•	Create an application database named NAV App DB based the original database Demo Database NAV (10-0), and connect the application database to the Dynamics NAV Server instance DynamicsNAV100.
•	Transform the original database Demo Database NAV (10-0) to be a tenant database by removing the application objects, and mount the tenant database on the Dynamics NAV Server instance DynamicsNAV100.
•	Create and mount a new tenant named MyTenantA.
Set-NAVServerInstance -ServerInstance DynamicsNAV100 -Stop
Export-NAVApplication –DatabaseServer 'MyDbServer' –DatabaseInstance 'NavDemo' –DatabaseName 'Demo Database NAV (10-0)' –DestinationDatabaseName 'NAV App DB'
Remove-NAVApplication –DatabaseServer 'MyDbServer' –DatabaseInstance 'NavDemo' –DatabaseName ‘Demo Database NAV (10-0)’
Set-NAVServerConfiguration -ServerInstance DynamicsNAV100 -KeyName multitenant -KeyValue true
Set-NAVServerConfiguration -ServerInstance DynamicsNAV100 -KeyName DatabaseName -KeyValue ‘NAV App DB’
Set-NAVServerInstance -ServerInstance DynamicsNAV100 -start
Mount-NAVTenantDatabase -ServerInstance DynamicsNAV100 -DatabaseName 'Demo Database NAV (10-0)' -Id 'MyTenantDb1'
Mount-NAVTenant -ServerInstance DynamicsNAV100 -TenantDatabaseId 'MyTenantDb1' -Id 'MyTenantA' -OverwriteTenantIdInDatabase
Sync-NAVTenant -ServerInstance DynamicsNAV100 -Id 'MyTenantA'
© 2017 Microsoft. All rights reserved.



When you run [!INCLUDE[navnowlong](includes/navnowlong_md.md)] Setup and install [!INCLUDE[nav_server](includes/nav_server_md.md)], you can provide configuration information that is then used as the configuration for the default [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.  

## See Also  
[Microsoft Dynamics NAV Server Administration Tool](Microsoft-Dynamics-NAV-Server-Administration-Tool.md)   
[Enhancing Microsoft Dynamics NAV Server Security](Enhancing-Microsoft-Dynamics-NAV-Server-Security.md)   
[Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)   
[Configuring Microsoft Dynamics NAV Help Server](Configuring-Microsoft-Dynamics-NAV-Help-Server.md)   
[How to: Specify When UI Elements Are Removed](How-to--Specify-When-UI-Elements-Are-Removed.md)   
[Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)   
[Configuring the Windows Client](Configuring-the-Windows-Client.md)   
[Configuring Dynamics NAV and the Excel Add-In](configuring-dynamics-nav-excel-addin.md)  
[Configuring Microsoft Dynamics NAV](Configuring-Microsoft-Dynamics-NAV.md)  

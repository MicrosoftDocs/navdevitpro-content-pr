---
title: Converting to Shared Schema
description: Provides and over view of the the shared schema data model.
ms.date: 10/16/2017
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
author: jswymer
---
# Converting to Shared Schema
Shared schema is a data model that shares database resources among tenants and companies. Shared schema optimizes the reuse of resources, such as execution plans, memory, and database connections.

Shared schema can be used in single tenant or multitenant deployment, although it is especially designed for a multitenant deployment.

## Overview
To help explain shared schema, let's first look at the conventional [!INCLUDE[navnow_md](includes/navnow_md.md)] data model, which is referred to as *separate schema*.

> [!TIP]
> A tenant is one or more companies, typically part of a business or legal entity, with common access to the application but requiring dedicated storage of business data in the database. In a single tenant deployment, the application and tenant business data are stored in the same database. In a multitenant deployment, the application is stored in one database, and the tenant business data in another database.

### Separate schema 
By default, [!INCLUDE[navnow_md](includes/navnow_md.md)] uses a *separate schema* data model. The separate schema has the following important characteristics: 

-  A database contains business data for one tenant only.

    In practical terms, a tenant is the database. This means that in a multitenant deployment, you have a separate database for each tenant. 
-  In the database, each company has a separate set of tables for storing business entity data, such as the Item, Customer, and Invoice tables (see figure 1). 

![Separate schema](media/separateschema2companies.png "Separate schema")

**Figure 1: Company business data with the separate schema**

### Shared schema

The shared schema data model has the following characteristics: 

-  A database can be shared by more than one tenant. Information about the tenants and their companies is stored in shared tables in the database (see figure 2).

   This is a change to the concept of a tenant/tenant database as compared with the separate schema model, which has one tenant per database (the tenant database). With shared schema, the tenant database is a container for one or more tenants, and each tenant is a unit of data in the tenant database (see figure 2).
   
   You can have multiple tenant databases among which you can mount, delete, and move tenants.  
-  In the database, companies share tables for storing business data.

    There is one set of business entity data tables for all companies and tenants in the database. For example, instead  of an Item table for each company, there is a single table that contains the data for all companies (see figure 3).

![Shared schema tenant data](media/SharedSchemaTenantTables.png "Shared schema tenant data")

**Figure 2: Tenant and company information with shared schema**

 ![Shared schema item table](media/SharedSchemaEntityTables.png "Shared schema item table")

**Figure 3: Company business data with shared schema**

## How to convert a tenant to shared schema
To convert to shared schema, you use the [Sync-NAVTenant cmdlet](https://go.microsoft.com/fwlink/?linkid=401399) that is included in the [nav_shell_md](includes/nav_shell_md.md). when you run the cmdlet, set the `-Mode` parameter to `ConvertToSharedSchema`as shown in the following example:

```
    Sync-NAVTenant -ServerInstance "DynamicsNAV" -Tenant "Tenant1" -Mode ConvertToSharedSchema
```

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

---
title: Managing tenants of a database that uses shared schema
description: Describes how to mount, configure, and upgrade tenants in a shared schema database. 
ms.date: 10/16/2017
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
author: jswymer
---
# Managing Tenants of a Shared Schema Database in a Multitenant Deployment
There are various tasks that you'll perform to set up and configure tenant databases and tenants against an application, and keep them running and up-to-date with the latest version.

You'll do most of these tasks by using the Powershell cmdlets that are available in the [!INCLUDE[navnow_md](includes/nav_shell_md.md)].

## Tenant Database and Tenant Management Cmdlets
After you convert the database to schared schema, you have access the following cmdlets for managing tenant databases and tenants:

### Tenant database cmdlets
|  Cmdlet  |  [!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]  |
|----------|-----------------------------------------------------------------------|
|[Mount-NAVTenantDatabase](Microsoft.Dynamics.NAV.Management/Mount-NAVTenantDatabase.md)| Mounts a tenant database on a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance that is connected to an application database.|
|[Dismount-NAVTenantDatabase](Microsoft.Dynamics.NAV.Management/Dismount-NAVTenantDatabase.md)|Dismounts a tenant database from a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Get-NAVTenantDatabase](Microsoft.Dynamics.NAV.Management/Get-NAVTenantDatabase.md)|Specifies a setting in an application-specific configuration file for a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Sync-NAVTenantDatabase](Microsoft.Dynamics.NAV.Management/Sync-NAVTenantDatabase.md)|Synchronizes a tenant database with the application database on a specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Test-NAVTenantDatabaseSchema](Microsoft.Dynamics.NAV.Management/Test-NAVTenantDatabaseSchema.md)| Checks for any errors in the tenant database schema.|

### Tenant cmdlets
|  Cmdlet  |  [!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]  |
|----------|-----------------------------------------------------------------------|
|[Mount-NAVtenant](Microsoft.Dynamics.NAV.Management/Mount-NAVtenant.md)|Mounts a tenant in the tenant database to the server instance that the tenant
database is mounted.|
|[Dismount-NAVtenant](Microsoft.Dynamics.NAV.Management/Dismount-NAVtenant.md)|Dismount a tenant in a tenant database from a server instance.
All active user sessions that access the tenant will end.|
|[New-NAVTenant](Microsoft.Dynamics.NAV.Management/New-NAVTenant.md)| Creates a new tenant in a tenant database. |
|[Copy-NAVTenantData](Microsoft.Dynamics.NAV.Management/Copy-NAVTenantData.md)|Copies tenant data from one tenant to another tenant in the same tenant database. |
|[Move-NAVTenant](Microsoft.Dynamics.NAV.Management/Move-NAVTenant.md)| Moves a tenant from a tenant database to another tenant database.|
|[Get-NAVTenant](Microsoft.Dynamics.NAV.Management/Get-NAVTenant.md)|Gets information about a tenant.|
|[Set-NAVTenant](Microsoft.Dynamics.NAV.Management/Set-NAVTenant.md)|Changes a tenant from a normal tenant to a buffer tenant, or acquires and release exclusive access to a tenant.|
|[Remove-NAVTenant](Microsoft.Dynamics.NAV.Management/Set-NAVTenant.md)|Deletes a tenant, including company and global data, from a tenant database.|
|[Start-NAVDataUpgrade](Microsoft.Dynamics.NAV.Management/Start-NAVDataUpgrade.md)|Starts the process for upgrading the data in the tenant database.|


## Getting started

This section outlines the basic steps for getting a tenant database and tenant running with a Dynamics NAV application. The steps assume that the application database and tenant database already exist. The tenant database either be an empty database or a valid Dynamics NAV 2018 database. 

1. Mount the application database to the server instance.

    Use the Mount-NAVApplication database to connect the server instance to Dynamics NAV application database. The application database contains tables that make up the application, as defined by its schema. The application database is assigned a version number.

2. Mount the tenant database to the the server instance.

    Use the Mount-NavTenantDatabase cmdlet to mount a tenant database on the same server instance as the application database.

    When a database is mounted for the first time on a Dynamics NAV Server instance, the server instance can process requests for data on the tenant database, however, the tenant database is not in the **Operational** state because it has not been synchronized with the application database on the server instance. This means that you cannot yet mount any tenants on the tenant database. 

3. Synchronize the tenant database with the application database.

    Use the Sync-NAVTenantDatabase cmdlet to synchronize the database schema in a tenant database with the schema in the application database. If successful, this will change the tenant database state to **Operational**, and allow you to tart mounting tenants. 
    
    When synchronized successfully, the application version of the application database on the server instance is then registered for support in tenant database.

4.  Add the existing tenant to the tenant database and mount it on the Server Instance.

    You use the Mount-NAVTenant cmdlet to  a tenant to a Dynamics NAV Server instance that is configured for
multitenancy.
 The parameter sets depend on whether the database is using the shared schema data model.

 If using the shared schema data model, a database (the tenant database) can contain one or more tenants. The
tenant database can be mounted on one or more Dynamics NAV Server instances. In this case, the Mount-Tenant cmdlet
takes a specific tenant from the tenant database, and mounts it on a specific server instance to which the tenant
database is mounted. The tenant database must already be mounted on the server instance, and the tenant must exist
in the database. You can create a tenant by using the New-NAVTenant cmdlet. To mount a tenant, you must specify
the Dynamics NAV Server instance name, tenant database ID, and tenant ID as a minimum. 

Creating New Tenants

Buffer Tenants

Versioning
A tenant database can be mounted on and synchronized with more than one server instance. The application database version of each server instance is registered for support in the tenant database. This enables you to have tenants in the tenant database that are using different application versions. This is useful, for example, when upgrading tenants to a newer application. An existing tenant can be upgraded to a newer application version by mounting it on the server instance that uses the newer application version, and then running a data upgrade.


## See Also  
[Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)   
[Migrating to Multitenancy](Migrating-to-Multitenancy.md)  
[Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)   
[Configuring Microsoft Dynamics NAV](Configuring-Microsoft-Dynamics-NAV.md)  

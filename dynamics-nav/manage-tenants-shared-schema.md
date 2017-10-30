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

### Tenant Database Cmdlets
|  Cmdlet  |  [!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]  |
|----------|-----------------------------------------------------------------------|
|[Mount-NAVTenantDatabase](Microsoft.Dynamics.NAV.Management/Mount-NAVTenantDatabase.md)| Mounts a tenant database on the specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Dismount-NAVTenantDatabase](Microsoft.Dynamics.NAV.Management/Dismount-NAVTenantDatabase.md)|Dismounts a tenant database on the specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Get-NAVTenantDatabase](Microsoft.Dynamics.NAV.Management/Get-NAVTenantDatabase.md)|Specifies a setting in an application-specific configuration file for a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Sync-NAVTenantDatabase](Microsoft.Dynamics.NAV.Management/Sync-NAVTenantDatabase.md)|Synchronizes a tenant database on the specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Test-NAVTenantDatabaseSchema](Microsoft.Dynamics.NAV.Management/Test-NAVTenantDatabaseSchema.md)| Checks for any errors in the tenant database schema.|

### Tenant Cmdlets
|  Cmdlet  |  [!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]  |
|----------|-----------------------------------------------------------------------|
|[Mount-NAVtenant](Microsoft.Dynamics.NAV.Management/Mount-NAVtenant.md)|-TenantDatabaseId and -Async parameters have been added.|
|[Dismount-NAVtenant](Microsoft.Dynamics.NAV.Management/Dismount-NAVtenant.md)|-InptTenantRuntimeSettings and -InputTenantSettings parameters have been removed.<br /><br />-ExclusiveAccessTicket parameter has been added.|
|[New-NAVTenant](Microsoft.Dynamics.NAV.Management/New-NAVTenant.md)| Creates a new tenant in a tenant database. |
|[Copy-NAVTenantData](Microsoft.Dynamics.NAV.Management/Copy-NAVTenantData.md)|Copies tenant data from one tenant to another tenant. |
|[Move-NAVTenant](Microsoft.Dynamics.NAV.Management/Move-NAVTenant.md)| Moves a tenant to another tenant database.|
|[Get-NAVTenant](Microsoft.Dynamics.NAV.Management/Get-NAVTenant.md)|-ForceRefresh parameter has been added |
|[Set-NAVTenant](Microsoft.Dynamics.NAV.Management/Set-NAVTenant.md)|Specifies settings for a tenant in a tenant database that is mounted on a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Sync-NAVTenant](Microsoft.Dynamics.NAV.Management/Sync-NAVTenant.md)|-CommitPerTable parameter added.|
|[Start-NAVDataUpgrade](Microsoft.Dynamics.NAV.Management/Start-NAVDataUpgrade.md)|-SingleTransaction, -SkipAppVersionCheck, and -SkipIfAlreadyUpgraded parameters have been added.|


## General Guidelines
1.  Mount the tenant database.
2.  Mount the tenant.
3.  Synchronize the tenant database.
4.  


## See Also  
[Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)   
[Migrating to Multitenancy](Migrating-to-Multitenancy.md)  
[Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)   
[Configuring Microsoft Dynamics NAV](Configuring-Microsoft-Dynamics-NAV.md)  

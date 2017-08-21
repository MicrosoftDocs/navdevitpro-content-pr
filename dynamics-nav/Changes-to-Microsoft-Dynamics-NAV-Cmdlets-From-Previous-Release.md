---
title: "Changes to Microsoft Dynamics NAV Cmdlets From Previous Release"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
author: jswymer
manager: edupont
ms.prod: "dynamics-nav-2017"
---
# Changes to Microsoft Dynamics NAV Cmdlets From Previous Release
The following sections provide an overview of the new, changed, and removed cmdlets in the [!INCLUDE[nav_shell](includes/nav_shell_md.md)] and [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] since the previous release.  

## Changes to [!INCLUDE[nav_shell](includes/nav_shell_md.md)] Cmdlets  

### New and changed cmdlets for administering the Dynamics NAV deployment

The following cmdlets are new in the Microsoft.Dynamics.Nav.Management module. 

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|
|[Copy-NAVTenantData](Microsoft.Dynamics.Nav.Management/Copy-NAVTenantData.md)|Copies tenant data from one tenant to another tenant. |
|[Dismount-NAVTenantDatabase](Microsoft.Dynamics.Nav.Management/Dismount-NAVTenantDatabase.md)|Dismounts a tenant database on the specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Get-NAVTenantDatabase](Microsoft.Dynamics.Nav.Management/Get-NAVTenantDatabase.md)|Specifies a setting in an application-specific configuration file for a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Mount-NAVTenantDatabase](Microsoft.Dynamics.Nav.Management/[Mount-NAVTenantDatabase.md)| Mounts a tenant database on the specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Move-NAVTenant](Microsoft.Dynamics.Nav.Management/Move-NAVTenant.md)| Moves a tenant to another tenant database.|
|[New-NAVTenant](Microsoft.Dynamics.Nav.Management/New-NAVTenant.md)| Creates a new tenant in a tenant database. |
|[Set-NavApplication](Microsoft.Dynamics.Nav.Management/Set-NavApplication.md)|Sets the application version or application family fields in the application database connected to the specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Set-NAVTenant](Microsoft.Dynamics.Nav.Management/Set-NAVTenant.md)|Specifies settings for a tenant in a tenant database that is mounted on a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Sync-NAVTenantDatabase](Microsoft.Dynamics.Nav.Management/Sync-NAVTenantDatabase.md)|Synchronizes a tenant database on the specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|

The following cmdlets have been changed in the Microsoft.Dynamics.Nav.Management module.

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|  
|[Dismount-NAVtenant](Microsoft.Dynamics.Nav.Management/Dismount-NAVtenant.md)|*InptTenantRuntimeSettings* and *InputTenantSettings* parameters have been removed.<br /><br />*ExclusiveAccessTicket* parameter has been added.|
|[Get-NAVTenant](Microsoft.Dynamics.Nav.Management/Get-NAVTenant.md)|*ForceRefresh* parameter has been added |
|[Mount-NAVtenant](Microsoft.Dynamics.Nav.Management/Mount-NAVtenant.md)|*TenantDatabaseId* and *Async* parameters have been added.|
|[Start-NAVDataUpgrade](Microsoft.Dynamics.Nav.Management/Start-NAVDataUpgrade.md)|*SingleTransaction* and *SkipAppVersionCheck* parameters have been added.|
|[Sync-NAVTenant](Microsoft.Dynamics.Nav.Management/Sync-NAVTenant.md)|*CommitPerTable* parameter added.|
|[New-NAVServerInstance](Microsoft.Dynamics.Nav.Management/New-NAVServerInstance.md)|*DeveloperServicesPort* has been added.|
|[New-NAVWebServerInstance](Microsoft.Dynamics.Nav.Management/New-NAVWebServerInstance.md)|*RegionFormat*, *Language*, and *Company* parameters have been removed.|

<!-- A number of other new cmdlets are available in the [!INCLUDE[nav_shell](includes/nav_shell_md.md)] but are not yet listed here. For a full list, see [Administration Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkID=626874).  -->

### New and changed cmdlets for administering Dynamics NAV Extensions
The following cmdlet are new in the Microsoft.Dynamics.Nav.Apps.Management module. 

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|  
|[Start-NAVAppDataUpgrade](Microsoft.Dynamics.Nav.Management/Start-NAVAppDataUpgrade.md)|Upgrades a NAV App to a specified tenant.|
|[Sync-NAVApp](Microsoft.Dynamics.Nav.Management/Sync-NAVApp.md)|Synchronizes an app to the specified tenant's database.|
|[Test-NAVTenantDatabaseSchema](Microsoft.Dynamics.Nav.Management/Test-NAVTenantDatabaseSchema.md)| Checks for any errors in the tenant database schema.|

<!--|[Get-NAVTableSynchSetupForDataUpgrade](Microsoft.Dynamics.Nav.Apps.Management/Get-NAVTableSynchSetupForDataUpgrade.md)|Gets information about the tables that will be modified, added, or removed during a tenant data upgrade on the specified  [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|-->

The following cmdlets have been changed in the Microsoft.Dynamics.Nav.Apps.Management module.

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|  
|[Get-NAVAppInfo](Microsoft.Dynamics.Nav.Apps.Management/Get-NAVAppInfo.md)|*TenantSpecificSettings*, *SymbolsOnly*, and *TenantId* parameters have been added.|
|[Get-NAVAppTenant](Microsoft.Dynamics.Nav.Management/Get-NAVAppTenant.md)|*IncludeFailed* and *Id* parameters have been added.|
|[Publish-NAVApp](Microsoft.Dynamics.Nav.Apps.Management/Publish-NAVApp.md)|*PackageType*, *ApplicationDatabaseName*, *ApplicationDatabaseServer*, *ApplicationDatabaseCredentials*, and *IdePath* parameters have been added.|
|[Repair-NAVApp](Microsoft.Dynamics.Nav.Apps.Management/Repair-NAVApp.md)|*PackageType*, *ApplicationDatabaseName*, *ApplicationDatabaseServer*, *ApplicationDatabaseCredentials*, *IdePath*, and *ServiceAccount* parameters have been added.|

## Changes to [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] Cmdlets  

### New cmdlets for creating Dynamics NAV extension packages
None. 
<!-- >  A number of other new cmdlets are available in the [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] but are not yet listed here. For a full list, see [Development Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkId=626875). -->

### Changed cmdlets  
The following cmdlets have been changed in the Microsoft.Dynamics.Nav.Apps.Tools module.
|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|  
|[Export-NAVAppTenantWebService](Microsoft.Dynamics.Nav.Apps.ToolsExport-NAVAppTenantWebService.md)|*ServiceName* parameter has been added.|

## See Also  
[Administration Cmdlets for Microsoft Dynamics NAV](Microsoft.Dynamics.Nav.Management/Microsoft.Dynamics.Nav.Management.md)  
[Development Cmdlets for Microsoft Dynamics NAV](Microsoft.Dynamics.Nav.Model.Tools/Microsoft.Dynamics.Nav.Model.Tools.md)  
[Administration Cmdlets for Microsoft Dynamics NAV Extensions](Microsoft.Dynamics.Nav.Apps.Tools/Microsoft.Dynamics.Nav.Apps.Tools.md)  
[Development Cmdlets for Microsoft Dynamics NAV Extensions](Microsoft.Dynamics.Nav.Apps.Tools/Microsoft.Dynamics.Nav.Apps.Tools.md)  
[Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)

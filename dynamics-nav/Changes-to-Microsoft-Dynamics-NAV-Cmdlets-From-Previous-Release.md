---
title: Cmdlets Changes From Previous Release
description: This article provides an overview of the new, changed, and removed cmdlets in the Administration Shell and Development Shell since previous release. 
ms.custom: na
ms.date: 10/25/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
author: jswymer
ms.prod: "dynamics-nav-2018"
---
# Changes to Microsoft Dynamics NAV Cmdlets From Previous Release

**Applies to:** [!INCLUDE[nav2018_md](includes/nav2018_md.md)]. [See [!INCLUDE[nav2017](includes/nav2017.md)] version](Changes-to-Microsoft-Dynamics-NAV-Cmdlets-From-Previous-Release-2017.md).

The following sections provide an overview of the new, changed, and removed cmdlets in the [!INCLUDE[nav_shell](includes/nav_shell_md.md)] and [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] since the previous release.  

## Changes to [!INCLUDE[nav_shell](includes/nav_shell_md.md)] Cmdlets  

### New and changed cmdlets for administering the Dynamics NAV deployment

The following cmdlets are new in the Microsoft.Dynamics.NAV.Management module. 


|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|
|[Restart-NAVServerInstance](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/Restart-NAVServerInstance)| Restarts a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance. |
|[Start-NAVServerInstance](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/Restart-NAVServerInstance)| Starts a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance. |
|[Stop-NAVServerInstance](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/Restart-NAVServerInstance)| Stops a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance. |
|[Set-NAVApplication](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/Set-NAVApplication)|Sets the application version or application family fields in the application database connected to the specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Set-NAVTenant](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/Set-NAVTenant)|Specifies settings for a tenant that is mounted on a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|

The following cmdlets have been changed in the Microsoft.Dynamics.NAV.Management module.

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|  
|[Dismount-NAVtenant](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/Dismount-NAVtenant)|-InptTenantRuntimeSettings and -InputTenantSettings parameters have been removed.<br /><br />-ExclusiveAccessTicket parameter has been added.|
|[Get-NAVTenant](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/Get-NAVTenant)|-ForceRefresh parameter has been added |
|[Mount-NAVtenant](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/Mount-NAVtenant)|-Async parameter has been added.|
|[Start-NAVDataUpgrade](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/Start-NAVDataUpgrade)|-SingleTransaction, -SkipAppVersionCheck, and -SkipIfAlreadyUpgraded parameters have been added.|
|[Sync-NAVTenant](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/Sync-NAVTenant)|-CommitPerTable parameter added.|
|[New-NAVServerInstance](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/New-NAVServerInstance)|-DeveloperServicesPort has been added.|
|[New-NAVWebServerInstance](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/New-NAVWebServerInstance)|-RegionFormat, -Language, and -Company parameters have been removed.|
|[Remove-NAVCompany](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/Remove-NAVCompany)|-ForceImmediateDataDeletion parameter has been added.|

<!-- A number of other new cmdlets are available in the [!INCLUDE[nav_shell](includes/nav_shell_md.md)] but are not yet listed here. For a full list, see [Administration Cmdlets for Microsoft Dynamics NAV Extensions](https://go.microsoft.com/fwlink/?LinkID=626874).  -->

### New and changed cmdlets for administering Dynamics NAV Extensions
The following cmdlet are new in the Microsoft.Dynamics.NAV.Apps.Management module. 

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|  
|[Start-NAVAppDataUpgrade](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.apps.management/Start-NAVAppDataUpgrade)|Upgrades a NAV App to a specified tenant.|
|[Sync-NAVApp](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.apps.management/Sync-NAVApp)|Synchronizes an app to the specified tenant's database.|

<!--|[Get-NAVTableSynchSetupForDataUpgrade](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.apps.management/Get-NAVTableSynchSetupForDataUpgrade)|Gets information about the tables that will be modified, added, or removed during a tenant data upgrade on the specified  [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|-->

The following cmdlets have been changed in the Microsoft.Dynamics.NAV.Apps.Management module.

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|  
|[Get-NAVAppInfo](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.apps.management/Get-NAVAppInfo)|-TenantSpecificSettings, -SymbolsOnly, and -TenantId parameters have been added.|
|[Get-NAVAppTenant](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.apps.management/Get-NAVAppTenant)|-IncludeFailed and -Id parameters have been added.|
|[Publish-NAVApp](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.apps.management/Publish-NAVApp)|-PackageType, -ApplicationDatabaseName, -ApplicationDatabaseServer, -ApplicationDatabaseCredentials, and -IdePath parameters have been added.|
|[Repair-NAVApp](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.apps.management/Repair-NAVApp)|-PackageType, -ApplicationDatabaseName, -ApplicationDatabaseServer, -ApplicationDatabaseCredentials, -IdePath, and -ServiceAccount parameters have been added.|
|[Uninstall-NAVApp](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.apps.management/Repair-NAVApp)|-ExclusiveAccessTicket parameter has been added.|

## Changes to [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] Cmdlets  

### Changed cmdlets for merging and modifying application object files 
The following cmdlets have been changed in the Microsoft.Dynamics.NAV.Model.Tools module.

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|  
|[Compare-NAVApplicationObject](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.model.tools/Compare-NAVApplicationObject)|-IgnoreDocumentation parameter has been added.|
|[New-NAVCrmTable](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.model.tools/New-NAVCrmTable)|-DeltaPath parameter has been added.|

<!-- >  A number of other new cmdlets are available in the [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] but are not yet listed here. For a full list, see [Development Cmdlets for Microsoft Dynamics NAV Extensions](https://go.microsoft.com/fwlink/?LinkId=626875). -->

<!--
### Changed cmdlets for creating extension packages  
The following cmdlets have been changed in the Microsoft.Dynamics.NAV.Apps.Tools module.
|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|  
|[Export-NAVAppTenantWebService](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.apps.tools/Export-NAVAppTenantWebService)|-ServiceName parameter has been added.|
-->

## See Also  
[Administration Cmdlets for Microsoft Dynamics NAV](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.management/Microsoft.Dynamics.NAV.Management.md)  
[Development Cmdlets for Microsoft Dynamics NAV](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.model.tools/Microsoft.Dynamics.NAV.Model.Tools.md)  
[Administration Cmdlets for Microsoft Dynamics NAV Extensions](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.apps.management/Microsoft.Dynamics.NAV.Apps.Management.md)  
[Development Cmdlets for Microsoft Dynamics NAV Extensions](https://docs.microsoft.com/powershell/module/microsoft.dynamics.nav.apps.tools/Microsoft.Dynamics.NAV.Apps.Tools.md)  
[Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)

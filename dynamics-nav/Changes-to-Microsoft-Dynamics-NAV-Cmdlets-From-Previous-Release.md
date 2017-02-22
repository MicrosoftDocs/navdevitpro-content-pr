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

### New cmdlets for administering the Dynamics NAV deployment  

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|
|[Get-NAVServerAppConfiguration](Microsoft.Dynamics.Nav.Management/Get-NAVServerAppConfiguration.md)|Returns the settings in an application-specific configuration file of a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[New-NAVServerAppConfiguration](Microsoft.Dynamics.Nav.Management/New-NAVServerAppConfiguration.md)|Creates a new server application specific configuration file.|
|[Set-NAVServerAppConfiguration](Microsoft.Dynamics.Nav.Management/Set-NAVServerAppConfiguration.md)|Specifies a setting in an application-specific configuration file for a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Import-NAVConfigurationPackageFile](Microsoft.Dynamics.Nav.Management/Import-NAVConfigurationPackageFile.md)|Imports a configuration package file into the application database.|
|[Remove-NAVConfigurationPackageFile](Microsoft.Dynamics.Nav.Management/Remove-NAVConfigurationPackageFile.md)| Removes a configuration package file from the application database.|
|[Import-NAVMembershipEntitlement](Microsoft.Dynamics.Nav.Management/Import-NAVMembershipEntitlement.md)|Imports the license entitlement data for a membership association.|
|[Update-NAVScheduledTaskList](Microsoft.Dynamics.Nav.Management/Update-NAVScheduledTaskList.md)|Updates the application-wide list of scheduled tasks with the information from the tenant database.|

<!-- A number of other new cmdlets are available in the [!INCLUDE[nav_shell](includes/nav_shell_md.md)] but are not yet listed here. For a full list, see [Administration Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkID=626874).  -->

### New cmdlets for administering Dynamics NAV Extensions

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|  
|[Get-NAVAppTableModification](Microsoft.Dynamics.Nav.Apps.Management/Get-NAVAppTableModification.md)|Gets information about the tabled added or modified by an extension based on the specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|[Remove-NAVAppsForTenant](Microsoft.Dynamics.Nav.Apps.Management/Remove-NAVAppsForTenant.md)| Removes all NAV Apps from the specified, unmounted tenant. This cmdlet should be run against tenants that are not mounted.|

<!--|[Get-NAVTableSynchSetupForDataUpgrade](Microsoft.Dynamics.Nav.Apps.Management/Get-NAVTableSynchSetupForDataUpgrade.md)|Gets information about the tables that will be modified, added, or removed during a tenant data upgrade on the specified  [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|-->

### Changed cmdlets  

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|  
|[Install-NAVApp](Microsoft.Dynamics.Nav.Apps.Management/Install-NAVApp.md)|*ExchangeAuthenticationMetadataLocation* parameter added.|
|[Mount-NAVTenant](Microsoft.Dynamics.Nav.Management/Mount-NAVTenant.md)|*ExchangeAuthenticationMetadataLocation* parameter added.|
|[Get-NAVTenant](Microsoft.Dynamics.Nav.Management/Mount-NAVTenant.md)|*ExchangeAuthenticationMetadataLocation* is returned.|
|[Start-NAVDataUpgrade](Microsoft.Dynamics.Nav.Management/Start-NAVDataUpgrade.md)|*Language* parameter added.|
|[Sync-NAVTenant](Microsoft.Dynamics.Nav.Management/Sync-NAVTenant.md)|*CommitPerTable* parameter added.|
|[New-NAVWebServerInstance](Microsoft.Dynamics.Nav.Management/New-NAVWebServerInstance.md)|The parameters *ACSUri*, *Language*, *RegionFormat*, and *Company* are deprecated. <BR /><BR />The *Language*, *RegionFormat*, and *Company* settings are now stored in system tables for users. Users can change the value of these settings from the **My Settings** page in the client. Administrators can globally change these settings by using User Personalization in the clients.<BR /><BR />The *ACSUri* has been replaced by the **WSFederationLoginEndpoint** key in the [!INCLUDE[nav_server](includes/nav_server_md.md)] configuration file, which you can set by using the [Set-NAVServerConfiguration cmdlet](Microsoft.Dynamics.Nav.Management/Set-NAVServerConfiguration.md).|

## Changes to [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] Cmdlets  

### New cmdlets for includes cmdlets for creating Dynamics NAV extension packages
 The following table includes the new cmdlets in the current release.  

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|------------|---------------------------------------|  
|[Export-NAVAppReportLayout](Microsoft.Dynamics.Nav.Apps.Tools/Export-NAVAppReportLayout.md)|Exports the specified custom report layout from the database to a file.|
|[Export-NAVAppTableData](Microsoft.Dynamics.Nav.Apps.Tools/Export-NAVAppTableData.md) | Exports data from a Microsoft Dynamics NAV database table to file.|
|[Export-NAVAppTenantWebService](Microsoft.Dynamics.Nav.Apps.Tools/Export-NAVAppTenantWebService.md)| Exports the specified web service from the database to a file.|

<!-- >  A number of other new cmdlets are available in the [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] but are not yet listed here. For a full list, see [Development Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkId=626875). -->

### Changed cmdlets  

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|
|------------|---------------------------------------|  
|[New-NAVCrmTable](Microsoft.Dynamics.Nav.Model.Tools/New-NAVCrmTable.md)|*AuthenticationType* parameter added.|

## See Also  
[Administration Cmdlets for Microsoft Dynamics NAV](Microsoft.Dynamics.Nav.Management/Microsoft.Dynamics.Nav.Management.md)  
[Development Cmdlets for Microsoft Dynamics NAV](Microsoft.Dynamics.Nav.Model.Tools/Microsoft.Dynamics.Nav.Model.Tools.md)  
[Administration Cmdlets for Microsoft Dynamics NAV Extensions](Microsoft.Dynamics.Nav.Apps.Tools/Microsoft.Dynamics.Nav.Apps.Tools.md)  
[Development Cmdlets for Microsoft Dynamics NAV Extensions](Microsoft.Dynamics.Nav.Apps.Tools/Microsoft.Dynamics.Nav.Apps.Tools.md)  
[Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)

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

### New Cmdlets  
 The following table includes the new cmdlets in the current release.  

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|------------|---------------------------------------|  
|Get-NAVServerAppConfiguration|Returns the settings in an application-specific configuration file of a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|  
|New-NAVServerAppConfiguration|Creates a new server application specific configuration file.|  
|Set-NAVServerAppConfiguration|Specifies a setting in an application-specific configuration file for a [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|  
|Get-NavTableSyncSetupForDataUpgrade|Gets information about the tables that will be modified, added, or removed during a tenant data upgrade on the specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|Import-NAVConfigurationPackageFile|Imports a configuration package file into the application database.|  
|Remove-NAVConfigurationPackageFile| Removes a configuration package file from the application database.|  
|Import-NAVMembershipEntitlement|Imports the license entitlement data for a membership association.|  
|Update-NAVScheduledTaskList|Updates the application-wide list of scheduled tasks with the information from the tenant database.|  

<!-- A number of other new cmdlets are available in the [!INCLUDE[nav_shell](includes/nav_shell_md.md)] but are not yet listed here. For a full list, see [Administration Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkID=626874).  -->

### New Cmdlets for Microsoft Dynamics NAV Extensions

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|------------|---------------------------------------|  
|Get-NAVAppTableModification|Gets information about the tabled added or modified by an extension based on the specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|Remove-NAVAppsForTenant| Removes all NAV Apps from the specified, unmounted tenant. This cmdlet should be run against tenants that are not mounted.|

### Changed Cmdlets  
 The following table includes the cmdlets that have changed in the current release.  

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|------------|---------------------------------------|  
|Mount-NAVTenant|*ExchangeAuthenticationMetadataLocation* parameter added.|  
[Start-NAVTenant|*Language* parameter added.|  
|Sync-NAVTenant|*CommitPerTable* parameter added.|  

## Changes to [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] Cmdlets  

### New Cmdlets  
 The following table includes the new cmdlets in the current release.  

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|------------|---------------------------------------|  
|Get-NavTableSyncSetupForDataUpgrade|Gets information about the tables that will be modified, added, or removed during a tenant data upgrade on the specified  [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|

### New Cmdlets for Microsoft Dynamics NAV Extensions
 The following table includes the new cmdlets in the current release.  

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|------------|---------------------------------------|  
|Export-NAVAppReportLayout|Exports the specified custom report layout from the database to a file.|  
|Export-NAVAppTableData | Exports data from a Microsoft Dynamics NAV database table to file.|  
|Export-NAVAppTenantWebService| Exports the specified web service from the database to a file.|
|Get-NAVAppTableModification|Gets information about the tabled added or modified by an extension based on the specified [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance.|
|Remove-NAVAppsForTenant| Removes all NAV Apps from the specified, unmounted tenant. This cmdlet should be run against tenants that are not mounted.|

<!-- >  A number of other new cmdlets are available in the [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] but are not yet listed here. For a full list, see [Development Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkId=626875). -->


## See Also  
 [Administration Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkID=296818)   
 [Development Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkId=397980)   
 [Administration Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkID=626874)   
 [Development Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkId=626875)   
 [Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)

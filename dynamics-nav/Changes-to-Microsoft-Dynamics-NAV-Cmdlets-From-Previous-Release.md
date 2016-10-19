---
title: "Changes to Microsoft Dynamics NAV Cmdlets From Previous Release"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.author: jswymer
manager: edupont
ms-prod: "dynamics-nav-2017"
---
# Changes to Microsoft Dynamics NAV Cmdlets From Previous Release
The following sections provide an overview of the new, changed, and removed cmdlets in the [!INCLUDE[nav_shell](includes/nav_shell_md.md)] and [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] since the previous release.  

## Changes to [!INCLUDE[nav_shell](includes/nav_shell_md.md)] Cmdlets  

### New Cmdlets  
 The following table includes the new cmdlets in the current release.  

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|------------|---------------------------------------|  
|Get-NAVServerAppConfiguration|Returns the settings in an application-specific configuration file of a Dynamics NAV Server instance.|  
|New-NAVServerAppConfiguration|Creates a new server application specific configuration file.|  
|Set-NAVServerAppConfiguration|Specifies a setting in an application-specific configuration file for a Dynamics NAV Server instance.|  
|Import-NAVConfigurationPackage|Imports a configuration package file into the application database.|  
|Update-NAVScheduledTaskList|Updates the application-wide list of scheduled tasks with the information from the tenant database.|  

> [!NOTE]  
>  A number of other new cmdlets are available in the [!INCLUDE[nav_shell](includes/nav_shell_md.md)] but are not yet listed here. For a full list, see [Administration Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkID=626874).  

### Changed Cmdlets  
 The following table includes the cmdlets that have changed in the current release.  

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|------------|---------------------------------------|  
|[Mount-NAVTenant](http://go.microsoft.com/fwlink/?LinkID=401372)|*ExchangeAuthenticationMetadataLocation* parameter added.|  
|[Start-NAVTenant](http://go.microsoft.com/fwlink/?LinkID=401399)|*Language* parameter added.|  
|[Sync-NAVTenant](http://go.microsoft.com/fwlink/?LinkID=401399)|*CommitPerTable* parameter added.|  

## Changes to [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] Cmdlets  

### New Cmdlets  
 The following table includes the new cmdlets in the current release.  

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|------------|---------------------------------------|  
|||  

> [!NOTE]  
>  A number of other new cmdlets are available in the [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] but are not yet listed here. For a full list, see [Development Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkId=626875).  

### Changed Cmdlets  
 The following table includes the cmdlets that have changed in the current release.  

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|------------|---------------------------------------|  
|None||  

### Removed Cmdlets  
 The following table includes the removed cmdlets in the current release.  

|Cmdlet|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|------------|---------------------------------------|  
|None||  

## See Also  
 [Administration Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkID=296818)   
 [Development Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkId=397980)   
 [Administration Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkID=626874)   
 [Development Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkId=626875)   
 [Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)

---
title: "Enable and dsiable Business Central self-service sign ups "
ms.custom: na
ms.date: 06/16/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: cb249654-c9be-482b-9a25-c26d7f229fc2
caps.latest.revision: 44
author: SusanneWindfeldPedersen
---

# Enable and dsiable Business Central self-service sign ups

Administrators for an Office 365 Tenant might not want their users to sign up for the [!INCLUDE[d365_bus_central_md](includes/d365_bus_central_md.md)] service without their awareness. You can complete the following procedure in Azure Active Directory to block individual user sign ups.  

To complete this procedure, you must install and use Azure AD cmdlets. For a list of MSOnline cmdlets that are available for Azure AD using Windows PowerShell, see [MSOnline](https://docs.microsoft.com/en-us/powershell/module/MSOnline/?view=azureadps-1.0&redirectedfrom=msdn).   

PowerShell commands can be used with Azure Active Directory to disable adhoc (self-service) subscriptions. Please note that these steps are not specific to [!INCLUDE[d365_bus_central_md](includes/d365_bus_central_md.md)]. This procedure will disable self-service subscriptions for any other products and services, as Azure AD does not provide tools for blocking sign-ups from specific products. Self-service signups can be re-enabled later.

To disable self-service signup, complete the following steps:

Sign in to Azure Active Directory using your admin credentials within the Azure Active Directory PowerShell command shell. These are the credentials that are used by the administrator of the Office 365 service.

$Msolcred = Get-credential

Connect-MsolService -Credential $MsolCred

The first line prompts you to enter your credentials:  
 
The second line connects to your Azure Active Directory using the credentials you provided.
After you’ve signed in, you can issue the command to disable self-service signups.

Set-MsolCompanySettings -AllowAdHocSubscriptions $false 

The following command shows whether self-service sign-ups are enabled in Azure Active Directory.

Get-MsolCompanyInformation | fl AllowAdHocSubscriptions 

After the command is entered, self-service signups are disabled for your Azure Active Directory. 

Users who try to sign up for Dynamics 365 Business Central or any other self-service products will see the following message: 

 

To re-enable self-service signups, follow the same steps to connect to your Azure Active Directly, then enter the following command:

Set-MsolCompanySettings -AllowAdHocSubscriptions $true 
  


## See Also  
[Differences in the Dynamics NAV Development Environments](devenv-differences.md)  
[AL Development Environment](devenv-reference-overview.md)  
[Developing Extensions in AL](devenv-dev-overview.md)  
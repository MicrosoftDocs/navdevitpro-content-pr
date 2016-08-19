---
title: "Troubleshooting: Running the Cmdlet for a Microsoft Dynamics NAV Web Server Hosted in Complex Network Topology"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f7af0f4b-8bc5-43e7-bf69-8305fc18b78e
caps.latest.revision: 3
manager: edupont
---
# Troubleshooting: Running the Cmdlet for a Microsoft Dynamics NAV Web Server Hosted in Complex Network Topology
Setting the trust relationship between the [!INCLUDE[nav_web](includes/nav_web_md.md)] and Microsoft Azure Active Directory requires specifying a remote endpoint for the [!INCLUDE[nav_web](includes/nav_web_md.md)] in the Azure AD Service Principal that is created for this web application. If the [!INCLUDE[navnow](includes/navnow_md.md)] Web server runs behind a DNS or another network component that changes or rewrites the web client’s address, the `Set-NavSingleSignOnWithOffice365` cmdlet is not able to compute this address, since it only runs on the local computer. To fix this issue, you can provide the cmdlet with the address as seen remotely for your [!INCLUDE[nav_web](includes/nav_web_md.md)]. The parameter you need to pass this address to is `NavWebAddress`.  
  
## See Also  
 [How to: Set up Microsoft Dynamics NAV for Single Sign\-on With Office 365 using Windows PowerShell](../Topic/How%20to:%20Set%20up%20Microsoft%20Dynamics%20NAV%20for%20Single%20Sign-on%20With%20Office%20365%20using%20Windows%20PowerShell.md)   
 [Authenticating Users with Azure Active Directory](Authenticating-Users-with-Azure-Active-Directory.md)
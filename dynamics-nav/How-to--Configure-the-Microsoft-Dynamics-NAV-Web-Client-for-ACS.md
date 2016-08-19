---
title:"How to: Configure the Microsoft Dynamics NAV Web Client for ACS"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod:"dynamics-nav-2017"
ms.assetid: 88e2b4aa-d614-43e0-a684-69ac9636a5ca
caps.latest.revision: 3
manager: tsiggaar
---
# How to: Configure the Microsoft Dynamics NAV Web Client for ACS
You configure the [!INCLUDE[nav_web](includes/nav_web_md.md)] for Access Control Service \(ACS\) by editing the web.config file. The web.config file is an .xml file that you can edit with a text editor, such as Notepad. By default, the web.config file is located in the [!INCLUDE[navnow_install](includes/navnow_install_md.md)]\\Web Client\\ folder.  
  
 Before you begin this procedure, you must perform the steps to configure your deployment for ACS. For more information, see [Authenticating Users with Microsoft Azure Access Control Service](Authenticating-Users-with-Microsoft-Azure-Access-Control-Service.md).  
  
### To configure the [!INCLUDE[nav_web](includes/nav_web_md.md)] for ACS  
  
1.  Edit the web server configuration file \(web.config\) for each instance of the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] that will be supporting users for ACS authentication.  
  
     A separate instance of the web.config file is maintained for each server instance. The default location for this file is [!INCLUDE[navnow_install](includes/navnow_install_md.md)]\\WebClient\\.  
  
    > [!CAUTION]  
    >  To ensure that your edits to web.config are saved, first open Notepad as an Administrator and then, in Notepad, open the settings file. To open Notepad as an Administrator, from the **Start** menu, right\-click **Notepad**, and then choose **Run as Administrator**.  
  
2.  In the web.config file, modify the following settings.  
  
    |Setting|Value|  
    |-------------|-----------|  
    |ClientServicesCredentialType|"AccessControlService"|  
    |ACSUri|Use the URI for your relying party application from the **Application Integration** section of the Access Control configuration. For more information, see [How to: Configure a Deployment for ACS](../Topic/How%20to:%20Configure%20a%20Deployment%20for%20ACS.md).|  
  
3.  After updating the values, save ClientUserSettings.config.  
  
## See Also  
 [Configure Microsoft Dynamics NAV Components for ACS](Configure-Microsoft-Dynamics-NAV-Components-for-ACS.md)
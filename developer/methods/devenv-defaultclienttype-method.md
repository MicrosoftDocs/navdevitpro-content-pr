---
title: "DEFAULTCLIENTTYPE Method"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: dynamics365-financials
ms.assetid: e2c0248d-0c38-4387-904b-442a1b65bea0
caps.latest.revision: 8
manager: edupont
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# DEFAULTCLIENTTYPE Method
Gets the default client that is configured for the [!INCLUDE[d365fin_server_md](../includes/d365fin_server_md.md)] instance that is used by the current session.  

## Syntax  

```  
[ClientType :=] DEFAULTCLIENTTYPE  
```  

## Property Value/Return Value  
 Type: ClientType  

 The default client, which be one of the following values:  

<!--NAV
|Value|[!INCLUDE[bp_tabledescription](../includes/bp_tabledescription_md.md)]|  
|-----------|---------------------------------------|  
|Windows|[!INCLUDE[nav_windows](../includes/nav_windows_md.md)]|  
|Web|[!INCLUDE[d365fin_web_md](../includes/d365fin_web_md.md)]|  
|Tablet|[!INCLUDE[d365fin_tablet_md](../includes/d365fin_tablet_md.md)] **Note:**  If you are running tablet.aspx in a browser, the ClientType will return Web.|  
|Desktop|[!INCLUDE[d365fin_web_md](../includes/d365fin_web_md.md)] running in the Dynamics NAV app. In this mode, the [!INCLUDE[d365fin_web_md](../includes/d365fin_web_md.md)] will have, for example, navigation pane and ribbon.|  
|Phone|[!INCLUDE[d365fin_phone_md](../includes/d365fin_phone_md.md)] **Note:**  If you are running phone.aspx in a browser, the ClientType will return Web.|  
-->

|Value|[!INCLUDE[bp_tabledescription](../includes/bp_tabledescription_md.md)]|  
|-----------|---------------------------------------|  
|Web|[!INCLUDE[d365fin_web_md](../includes/d365fin_web_md.md)]|  
|Tablet|[!INCLUDE[d365fin_tablet_md](../includes/d365fin_tablet_md.md)] (app). **Note:**  If you are running tablet.aspx in a browser, the ClientType will return Web.|  
|Desktop|[!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] desktop (PC) client (app).|  
|Phone|[!INCLUDE[d365fin_phone_md](../includes/d365fin_phone_md.md)] (app). **Note:**  If you are running phone.aspx in a browser, the ClientType will return Web.|  


## Remarks  
 <!--NAV The default client is specified by the *DefaultClient* setting in the CustomSettings.config file for the [!INCLUDE[d365fin_server_md](../includes/d365fin_server_md.md)] instance. You can view and change the setting by opening the CustomSettings.config file directly or using the [!INCLUDE[nav_admin](../includes/nav_admin_md.md)]. For more information, see [Configuring Microsoft Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV-Server.md).-->  

 You can use DEFAULTCLIENTTYPE in a [GETURL Method](devenv-GETURL-Method.md) call to get the URL of the default client.  

## Example  
 In the following example, DEFAULTCLIENTTYPE is used to return the default client type that is configured for the [!INCLUDE[d365fin_server_md](../includes/d365fin_server_md.md)] instance that is used by the current session.  

```  
IF DEFAULTCLIENTTYPE = CLIENTTYPE::Web THEN  
  Message('The default client is Web client');  
```  

## Example  
 In the following example, DEFAULTCLIENTTYPE is used as a parameter in the GETURL method to return the URL of the default client that is configured for the [!INCLUDE[d365fin_server_md](../includes/d365fin_server_md.md)] instance.  

```  
url := GETURL(DEFAULTCLIENTTYPE);  
MESSAGE('The URL is %1.', url);  
```  

## See Also  
 [Session Methods](devenv-session-methods.md)

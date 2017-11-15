---
title: "Enabling APIs for Microsoft Dynamics NAV 2018"
description: "Describing the steps you must go through to enable access to the APIs."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/15/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

# Enabling APIs for Microsoft Dynamics NAV 2018
Dynamics NAV and Dynamics 365 for Financials expose an API that makes it possible to integrate with other services. To enable integration with these APIs, you must go through a few steps to enable the access for [!INCLUDE[navnow](includes/navnow_md.md)].

## Enable access to APIs

1. Open Microsoft Dynamics NAV 2018 Administration tool. 
2. Expand the **OData Services** tab, and select the **Enable OData Services** checkbox first, then select the **Enable API Services** checkbox.
3. Check that the values for the **OData Base URL** and **Port** are entered correctly.  
    > [!NOTE]  
    >  When exposing a web service, you must open the port for other consumers of your web service to access it. You can have your system administrator add the port through Windows Firewall on the computer running [!INCLUDE[nav_server](includes/nav_server_md.md)]. The default port for ODdata web services is 7048.
4. In [!INCLUDE[navnow](includes/navnow_md.md)], search for **API Setup** and then choose the related link.
5. On the **API Setup** page, choose the **Integrate APIs** button.  
    > [!NOTE] 
    > This will start a process of populating all the integration tables with records for all APIs. The process can take several minutes.

## Accessing the endpoint
Once you have the API access enabled, you can write code that integrates your web service or SaaS solution with Microsoft Dynamics NAV. Creating your integration through an API provides simple access to the supported functionality in a single endpoint, giving you a simplified experience for creating a single app with integrations across multiple Microsoft products. 

||Dynamics 365 for Financials (online)|||Microsoft Dynamics NAV 2018 (on-prem)|
|--|--|--|--|--|
|Means of connection|Microsoft Graph|Common endpoint service|Direct tenant|Direct installation|
|Usage|Production|Production|Rapid development and testing only|Production|
|Endpoint|`https://graph.microsoft.com/financials/beta/`| `https://api.financials.dynamics.com`|`https://<tenant url>:7048/MS/api/<API version>/`<br>  Example: `https://contoso.com:7048/api/beta`|OData base URL in installation: <br> `https://<base URL>:<port>/v1.0/api/<API version>/` <br> Example: `https://nav.contoso.com:7048/v1.0/api/beta/` <br> Must be exposed through a firewall.|
|Availability|Always enabled|Always enabled|Always enabled|Disabled by default.<br> Must be enabled by the administrator.|
|Authentication|Azure Active Directory (AAD)|Azure Active Directory (AAD)|Basic authentication. Username and web service access key as password.|Basic authentication.<br> Username and web service access key as password.|
|API/Data access|Based on user's permissions|Based on user's permissions|Based on user's permissions|Based on user's permissions|
|API update cycle|Monthly|Monthly|Monthly|Hotfixes installed by partner|
|Development instance|Sign up for a tenant at http://portal.microsoft.com|Sign up for a tenant at http://portal.microsoft.com|Sign up for a tenant at http://portal.microsoft.com|Get Docker instance|

## See Also
[API Documentation (Preview)](fin-graph/index.md)  
[Developing Connect Apps for Dynamics 365 for Financials](developer/devenv-develop-connect-apps-for-fin.md)  
[Configuring Microsoft Dynamics NAV Server](configuring-microsoft-dynamics-nav-server.md)  
[Microsoft Dynamics NAV Web Services Overview](microsoft-dynamics-nav-web-services-overview.md)  
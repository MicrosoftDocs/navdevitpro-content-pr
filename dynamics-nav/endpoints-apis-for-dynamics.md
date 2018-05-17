---
title: "Endpoints for the APIs for Microsoft Dynamics NAV and Microsoft Dynamics 365 Business Central"
description: "Describing the steps you must go through to enable access to the APIs in on-prem and cloud product versions."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 03/23/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
---

# Endpoints for the APIs for Microsoft Dynamics NAV and Microsoft Dynamics 365 Business Central
[!INCLUDE[navnow](includes/navnow_md.md)] and [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] expose an API that makes it possible to integrate with other services. To enable integration with these APIs, for [!INCLUDE[navnow](includes/navnow_md.md)] you must go through a few steps to enable the access first. For more information about these steps, see [Enabling APIs for Microsoft Dynamics NAV](enabling-apis-for-dynamics-nav.md).

## Accessing the endpoint
Once you have the API access enabled, you can write code that integrates your web service or SaaS solution with [!INCLUDE[navnow](includes/navnow_md.md)]. Creating your integration through an API provides simple access to the supported functionality in a single endpoint, giving you a simplified experience for creating a single app with integrations across multiple Microsoft products.

||[!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]|||Microsoft Dynamics<br> NAV 2018|
|--|--|--|--|--|
|**Means of connection**|**Microsoft Graph (coming)**|**Common endpoint service**|**Direct tenant**|**Direct installation**|
|**Usage**|Production|Production|Rapid development and testing only|Production|
|**Endpoint**|`https://`<br>`graph.microsoft.com`<br>`/businesscentral/beta/`| `https://`<br>`api.businesscentral.dynamics.com/`<br> `v1.0/api/beta`|`https://`<br>`api.businesscentral.dynamics.com/`<br>`v1.0/<user domain name>/api/beta`<br>  Example: `https://`<br>`api.businesscentral.dynamics.com/`<br> `v1.0/cronus.com/api/beta`|OData base URL in installation: <br> `https://`<br>`<base URL>:<port>/v1.0/api/<API version>/` <br> Example: `https://`<br>`nav.contoso.com:7048/`<br>`v1.0/api/beta/` <br> Must be exposed through a firewall.|
|**Availability**|Always enabled|Always enabled|Always enabled|Disabled by default.<br> Must be enabled by the administrator.|
|**Authentication**|Azure Active Directory<br> (AAD)|Azure Active Directory<br> (AAD)|Basic authentication.<br> Username and [web service<br> access key](developer/devenv-develop-connect-apps-for-fin.md) as password.|Basic authentication.<br> Username and [web service<br> access key](developer/devenv-develop-connect-apps-for-fin.md) as password.|
|**API/Data access**|Based on user's<br> [permissions](permissions-on-database-objects.md)|Based on user's<br> [permissions](permissions-on-database-objects.md)|Based on user's<br> [permissions](permissions-on-database-objects.md)|Based on user's<br> [permissions](permissions-on-database-objects.md)|
|**API update cycle**|Monthly|Monthly|Monthly|Hotfixes installed by partner|
|**Development instance**|Sign up for a [tenant](https://go.microsoft.com/fwlink/?linkid=847861)|Sign up for a [tenant](https://go.microsoft.com/fwlink/?linkid=847861)|Sign up for a [tenant](https://go.microsoft.com/fwlink/?linkid=847861)|Get [Docker](https://aka.ms/navdeveloperpreview) instance|

## See Also
[API Documentation (Preview)](fin-graph/index.md)  
[Developing Connect Apps for Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-develop-connect-apps)    
[Configuring Microsoft Dynamics NAV Server](configuring-microsoft-dynamics-nav-server.md)  
[Microsoft Dynamics NAV Web Services Overview](microsoft-dynamics-nav-web-services-overview.md)  

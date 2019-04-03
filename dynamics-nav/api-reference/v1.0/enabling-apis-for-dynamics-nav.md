---
title: "Enabling APIs for Microsoft Dynamics NAV"
description: "Describing the steps you must go through to enable access to the APIs."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 04/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

# Enabling the APIs for Dynamics 365 Business Central
[!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] exposes an API that makes it possible to integrate with other services. To enable integration with these APIs, you must go through a few steps to enable the access for [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)].

> [!IMPORTANT]  
> REST programming is not natively supported in C/SIDE. In order to run the APIs you must add the REST dependent types manually. Existing W1 objects can compile and load, but some .NET types cannot be loaded into the C/SIDE Development environment variable editor due to missing server dependencies.

## Enable access to the APIs
1. Open [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] Administration tool. 
2. Expand the **OData Services** tab, and select the **Enable OData Services** checkbox first, then select the **Enable API Services** checkbox.
3. Check that the values for the **OData Base URL** and **Port** are entered correctly.  
    When exposing a web service, you must open the port for other consumers of your web service to access it. You can have your system administrator add the port through Windows Firewall on the computer running [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] server. The default port for OData web services is 7048.
4. In [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)], search for **API Setup** and then choose the related link.
5. On the **API Setup** page, choose the **Integrate APIs** button.  
    This will start a process of populating all the integration tables with records for all APIs. The process can take several minutes.

Depending on where you want to access the APIs from, you must specify the correct endpoint. For more information, see [Endpoints for APIs](endpoints-apis-for-dynamics.md).

## See Also
[Developing Connect Apps for Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-develop-connect-apps)  
[Configuring Microsoft Dynamics NAV Server 2018](../../configuring-microsoft-dynamics-nav-server.md)  
[Microsoft Dynamics NAV Web Services Overview](../../microsoft-dynamics-nav-web-services-overview.md)  
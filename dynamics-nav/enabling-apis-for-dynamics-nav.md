---
title: "Enabling APIs for Microsoft Dynamics NAV 2018"
description: "Describing the steps you must go through to enable access to the APIs."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/10/2017
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
Microsoft Dynamics 365 for Financials exposes an API that makes it possible to integrate with other services. To enable integration with these APIs, you must go through a few steps to enable the access for [!INCLUDE[navnow](includes/navnow_md.md)].

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

## See Also
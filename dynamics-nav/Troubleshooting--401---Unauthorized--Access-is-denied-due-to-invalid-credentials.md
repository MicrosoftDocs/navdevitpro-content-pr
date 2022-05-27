---
title: Troubleshooting - 401-Unauthorized-Access is denied due to invalid credentials
description: Learn how the client is disconnected from the server instance and event log includes a warning event. 
ms.custom: na
ms.date: 03/14/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
author: jswymer
---
# Troubleshooting: 401 - Unauthorized: Access is denied due to invalid credentials. 

When you try to access the Microsoft Dynamics NAV Web client, you get the following error:

`401 - Unauthorized: Access is denied due to invalid credentials. You do not have permission to view this directory or page using the credentials that you supplied.`

## Resolution
This error typically occurs when authentication is not configured correctly between the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] (Microsoft Dynamics NAV Web client site on IIS) and [!INCLUDE[nav_server](includes/nav_server_md.md)]. To resolve this error, verify that the following conditions are met:

- The credential type to use for authenticating users is configured correctly in [!INCLUDE[nav_server](includes/nav_server_md.md)] and in the web.config file of the Microsoft Dynamics NAV Web client site on IIS.
    For example, if the Microsoft Dynamics NAV Web client site is configured for Windows credential type, the [!INCLUDE[nav_server](includes/nav_server_md.md)] must also be configured for Windows credential type.
- The correct authentication method is enabled on the Microsoft Dynamics NAV Web client site on IIS.
    - For the Windows credential type, enable Windows authentication.
    - For the UserName and NavUserPassword credential types, enable both Forms authentication and Anonymous authentication.
- For Windows authentication, the correct authentication providers are configured on the Microsoft Dynamics NAV Web client site on IIS.

For step-by-step instructions about how change or verify these settings, see [Configuring the Credential Type on the Microsoft Dynamics NAV Web Client Website](How-to--Configure-Authentication-of-Microsoft-Dynamics-NAV-Web-Client-Users.md).
 
 ## See Also    
[Troubleshooting the Microsoft Dynamics NAV Web Client Installation](Troubleshooting-the-Microsoft-Dynamics-NAV-Web-Client-Installation.md)   
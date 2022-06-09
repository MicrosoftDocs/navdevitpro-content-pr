---
title: "Troubleshooting: The SAML2 token is not valid because its validity period has ended."
description: This topic contains information on how to troubleshoot The SAML2 token is not valid because its validity period has ended.
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: b8612c03-8366-4334-94c0-d409f1c4a10b
caps.latest.revision: 8
author: jswymer
---
# Troubleshooting: The SAML2 token is not valid because its validity period has ended

When using Azure Active Directory authentication, while working in the client, users get an error similar to the following: 

**Connection is not longer available or was lost**

The event log includes the following error for the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance:

**The SAML2 token is not valid because its validity period has ended.** 

## Resolution  

This error occurs because the security token that used by Azure AD has exceeded its specified lifetime. By default, the lifetime, which is determined by Azure AD, is 1 hour. However, the [!INCLUDE[nav_server](includes/nav_server_md.md)] includes a configuration setting called `ExtendedSecurityTokenLifetime` which you can set to add additional time to the security token lifetime. If this issue becomes a problem, you can increase the value of the  `ExtendedSecurityTokenLifetime` setting. Before you do this though, we recommend that you read more about the Azure AD token lifetime policies at [Configurable token lifetimes in Azure Active Directory](/azure/active-directory/develop/active-directory-configurable-token-lifetimes).


## See Also  
 [Configuring Microsoft Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV-Server.md)
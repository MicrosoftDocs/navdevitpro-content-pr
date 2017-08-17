---
title: Features not implemented in on-premises deployments
author: edupont04
manager: edupont
ms.author: edupont
ms.custom: na
ms.date: 08/17/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
---
# Features not implemented in on-premises deployments of [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]

This topic lists features that are not available in on-premises deployments of [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]. The topic is divided into two sections:
- The first section lists features that are available under very specific circumstances in on-premises deployments.  
- The second section lists features that are not intended for use with on-premises deployments. There are no plans to implement these features.  

## Features that require specific circumstances
The following features are not available in all on-premises deployments because they require specific circumstances.  

| **Feature**                      |**Description**                                  |
|----------------------------------|-------------------------------------------------|
| Read/write data with Excel add-in       |The Excel add-in that enables update of data require Azure Active Directory as the authentication mechanism. |

## Features not intended for use in on-premises deployments
The following features are not intended for use in on-premises deployments. There are no plans to implement these features in on-premises deployments.

| **Feature**                      |**Description**                                  |
|----------------------------------|-------------------------------------------------|
| Help mapping       |Online deployments of [!INCLUDE[d365fin](includes/d365fin_md.md)] use a system table to look up Help on the docs.microsoft.com site. This is not supported for on-premises deployments, where only Help Server is supported.|

## See Also
[Configuring Microsoft Dynamics NAV](Configuring-Microsoft-Dynamics-NAV.md)

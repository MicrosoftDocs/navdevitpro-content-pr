---
title: "Upgrading to Microsoft Dynamics NAV 2018"
ms.custom: na
ms.date: 05/04/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.author: jswymer
author: jswymer
ms.prod: "dynamics-nav-2018"
---
# Upgrading to [!INCLUDE[nav2018_md](includes/nav2018_md.md)]

**Applies to:** [!INCLUDE[nav2018_md](includes/nav2018_md.md)]. [See [!INCLUDE[nav2017](includes/nav2017.md)] version](Upgrading-to-Microsoft-Dynamics-NAV-2017.md).

This topic provides an overview of how to upgrade to [!INCLUDE[navnowlong](includes/navnowlong_md.md)]. The upgrade process depends on different factors, such as the version of [!INCLUDE[navnow](includes/navnow_md.md)] that you are upgrading from, and the degree to which your solution differs from the standard version of [!INCLUDE[navnow](includes/navnow_md.md)]. The mains tasks range from converting the database to upgrading application code and data.

Use the following table to determine the procedures that you must complete for your upgrade scenario.

|  Scenario  |  Procedures  |  
|------------|--------------|  
|Full upgrade from one of the following versions:<ul><li>[!INCLUDE[navcrete](includes/navcrete_md.md)]</li><li>[!INCLUDE[navcorfu](includes/navcorfu_md.md)]</li><li>[!INCLUDE[nav2017](includes/nav2017.md)]</li></ul>|<ol><li>[Upgrade the Application Code](Upgrading-the-Application-Code.md)</li><li>[Upgrade the Data](Upgrading-the-Data.md)</li></ol>|  
|Full upgrade from one of the following versions:<ul><li>[!INCLUDE[nav7long](includes/nav7long_md.md)]</li><li>[!INCLUDE[navsicily](includes/navsicily_md.md)]</li></ul>|<ol><li>Upgrade to [!INCLUDE[navnowlong](includes/navnowlong_md.md)] Cumulative Update 2:</li><ol><li>[Download [!INCLUDE[navnowlong](includes/navnowlong_md.md)] CU2](https://support.microsoft.com/help/4078580/cumulative-update-02-for-microsoft-dynamics-nav-2018-build-20348?preview).<li>[Upgrade the Application Code](Upgrading-the-Application-Code.md)</li><li>[Upgrade the Data](Upgrading-the-Data.md)</li></ol><li>Upgrade to the latest [!INCLUDE[navnowlong](includes/navnowlong_md.md)] cumulative update (CU):</li><ol><li>[Upgrade the Application Code](Upgrading-the-Application-Code.md)</li><li>[Upgrade the Data](Upgrading-the-Data.md)</li></ol></ol>|  
|Full upgrade from one of the following versions:<ul><li>  [!INCLUDE[nav2009sp1](includes/nav2009sp1_md.md)]</li><li>[!INCLUDE[nav2009r2](includes/nav2009r2_md.md)]</li><li>  [!INCLUDE[nav_5](includes/nav_5_md.md)]</li><li>   [!INCLUDE[nav_4](includes/nav_4_md.md)]</li></ul>|<ol><li>Upgrade to [!INCLUDE[nav7long](includes/nav7long_md.md)].</br></br>For more information, see [Upgrading to Microsoft Dynamics NAV 2013](https://go.microsoft.com/fwlink/?LinkId=510382) in the MSDN Library.</br></br>Alternatively, you can upgrade from [!INCLUDE[nav2009sp1](includes/nav2009sp1_md.md)] or [!INCLUDE[nav2009r2](includes/nav2009r2_md.md)] to [!INCLUDE[navcrete](includes/navcrete_md.md)] as described on the [Dynamics NAV Team Blog](https://blogs.msdn.microsoft.com/nav/2014/11/09/cumulative-update-1-for-microsoft-dynamics-nav-2015-has-been-released/).</li><li>Upgrade to [!INCLUDE[navnowlong](includes/navnowlong_md.md)] Cumulative Update 2.</li><ol><li>[Download [!INCLUDE[navnowlong](includes/navnowlong_md.md)] CU2](https://support.microsoft.com/help/4078580/cumulative-update-02-for-microsoft-dynamics-nav-2018-build-20348?preview).<li>[Upgrade the Application Code](Upgrading-the-Application-Code.md)</li><li>[Upgrade the Data](Upgrading-the-Data.md)</li></ol><li>Upgrade to the latest [!INCLUDE[navnowlong](includes/navnowlong_md.md)] cumulative update (CU) by following steps a and b above.</li></ol>After the upgrade, links between interaction records and logged email messages is lost. To resolve this issue, the administrator has to log all mails again to restore the links. For more information, see [Logging Interaction Links are Lost When You Upgrade from Microsoft Dynamics NAV 2009 R2](https://msdn.microsoft.com/library/hh167032%28v=nav.90%29.aspx#LoggingInteractionLinks).|
|Technical upgrade of [!INCLUDE[navnowlong](includes/navnowlong_md.md)] database to a new platform version with no application changes, such as with a cummulative update|<ul><li>[Converting a Database](Converting-a-Database.md)</li></ul></br>You can also use this procedure to convert a previous [!INCLUDE[navnow](includes/navnow_md.md)] database to [!INCLUDE[nav2018_md](includes/nav2018_md.md)] technical requirements, and then upgrade the application and data later.|  

Before you begin the upgrade process, see [Upgrade Considerations](Upgrade-Considerations.md) for tips about things to consider when you prepare to upgrade to [!INCLUDE[navnowlong](includes/navnowlong_md.md)].

## Automating the Upgrade Process using Sample Windows PowerShell Scripts
You can use [!INCLUDE[wps_2](includes/wps_2_md.md)] scripts to help you upgrade to [!INCLUDE[navnowlong](includes/navnowlong_md.md)]. You can use automation to upgrade a single [!INCLUDE[navnow](includes/navnow_md.md)] database as well as multiple [!INCLUDE[navnow](includes/navnow_md.md)] databases that use the same application. [!INCLUDE[navnowlong](includes/navnowlong_md.md)] provides sample scripts that you can adapt for your deployment architecture.
For more information, see [Automating the Upgrade Process using Sample Windows PowerShell Scripts](Automating-the-Upgrade-Process-using-Sample-Windows-PowerShell-Scripts.md).  


<!-- https://mbs.microsoft.com/partnersource/global/deployment/downloads/product-releases/msdnav2018download -->

## See Also  
[Product and Architecture Overview](Product-and-Architecture-Overview.md)   
[Migrating to Multitenancy](Migrating-to-Multitenancy.md)   
[Deployment](Deployment.md)  
[Transforming Forms to Pages](https://go.microsoft.com/fwlink/?LinkId=510383)

---
title: "Upgrading to Microsoft Dynamics NAV 2016"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 015dd873-0887-4ac6-a5cd-809778286099
caps.latest.revision: 16
manager: edupont
---
# Upgrading to Microsoft Dynamics NAV 2016
This section describes how to upgrade from [!INCLUDE[nav7long](includes/nav7long_md.md)], [!INCLUDE[navsicily](includes/navsicily_md.md)], or [!INCLUDE[navcrete](includes/navcrete_md.md)] to [!INCLUDE[navnowlong](includes/navnowlong_md.md)]. If you have an earlier version, such as [!INCLUDE[nav2009sp1](includes/nav2009sp1_md.md)], [!INCLUDE[nav2009r2](includes/nav2009r2_md.md)], [!INCLUDE[nav_5](includes/nav_5_md.md)], or [!INCLUDE[nav_4](includes/nav_4_md.md)], you must first upgrade that version to [!INCLUDE[nav7long](includes/nav7long_md.md)]. For more information, see [Upgrading to Microsoft Dynamics NAV 2013](http://go.microsoft.com/fwlink/?LinkId=510382) in the MSDN Library.  
  
> [!TIP]  
>  You can also upgrade from [!INCLUDE[nav2009sp1](includes/nav2009sp1_md.md)] or [!INCLUDE[nav2009r2](includes/nav2009r2_md.md)] to [!INCLUDE[navcrete](includes/navcrete_md.md)] as described on the [Dynamics NAV Team Blog](https://blogs.msdn.microsoft.com/nav/2014/11/09/cumulative-update-1-for-microsoft-dynamics-nav-2015-has-been-released/). Then you can use the automated upgrade process to upgrade to [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  
  
 To upgrade to [!INCLUDE[navnowlong](includes/navnowlong_md.md)], you must complete the following main steps:  
  
-   Convert the database.  
  
-   Upgrade the code.  
  
-   Upgrade the data.  
  
## In This Section  
  
-   [Upgrade Considerations](Upgrade-Considerations.md)  
  
-   [Converting a Database](Converting-a-Database.md)  
  
-   [Upgrading the Application Code](Upgrading-the-Application-Code.md)  
  
-   [Upgrading the Data](Upgrading-the-Data.md)  
  
-   [Automating the Upgrade Process using Sample Windows PowerShell Scripts](Automating-the-Upgrade-Process-using-Sample-Windows-PowerShell-Scripts.md)  
  
> [!IMPORTANT]  
>  If you upgrade from [!INCLUDE[nav2009r2](includes/nav2009r2_md.md)] or earlier to [!INCLUDE[nav7long](includes/nav7long_md.md)] or later, the link between interaction records and logged email messages is lost. To resolve this issue, the administrator has to log all mails again to restore the links. For more information, see [Logging Interaction Links are Lost When You Upgrade from Microsoft Dynamics NAV 2009 R2](../Topic/Troubleshooting:%20Email%20Logging.md#LoggingInteractionLinks).  
  
## Related Sections  
 [Product and Architecture Overview](Product-and-Architecture-Overview.md)  
  
 [Migrating to Multitenancy](Migrating-to-Multitenancy.md)  
  
 [Deployment](Deployment.md)  
  
## See Also  
 [Transforming Forms to Pages](http://go.microsoft.com/fwlink/?LinkId=510383)
---
title: Personalizing Pages | Microsoft Docs
description: Learn how to customize the user interface to suit your way of working.
services: project-madeira
documentationcenter: ''
author: jswymer

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customize, personalize, personalization, hide columns, remove fields, move fields
ms.date: 07/26/2017
ms.author: jswymer

---
# Personalizing Your Workspace - Overview
[!INCLUDE[personalization_md](includes/personalization_md.md)]
You can customize, or *personalize*, your workspace to suit your work and preferences by changing pages so that they display only the information you need, where you need it. The personalization changes that you make will only affect what you see, not what other users see.

You can personalize your workspace by using the [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)] and [!INCLUDE[nav_web_md](includes/nav_web_md.md)]. The personlization changes that you make in these clients will also be seen in the [!INCLUDE[nav_phone_md](includes/nav_phone_md.md)] and [!INCLUDE[nav_web_md](includes/nav_phone_md.md)].
  
> [!NOTE]  
> The administrator in your company may have already customized your user interface to a role-specific layout for all users who have the same profile as you and use the same Role Center. Personalizations that you make to your workspace are saved under your user account, so they will be preserved even if an administrator rolls out a new set of role-specific layouts  in your company. For more information, see Configure the User Interface.

## Comparing personalization in the Dynamics NAV Windows and Web clients
Depending on the page, you can personalize many parts of the user interface, such as what fields or columns are shown and where they are placed, what actions are included on the ribbon, and more. Many of these things you can do in both the  [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)] and [!INCLUDE[nav_web_md](includes/nav_web_md.md)]. The following table provides an overview of the personalization capabilities in each client.

|  Personalize  ||  Windows client  |  Web client  |
|---------------|-|------------------|--------------|
|Fields in FastTabs||||
||Add, move, remove |x|x|
||Show in collapsed header|x||
||Hide under **Show more fields** action|x||
|Lists or document lines ||||
||Add, move, remove columns  |x|x|
||Add, move, remove freeze pane  |x|x|
|FactBoxes|||
||Move, remove|x|x|
||Add|x||
||Add, move, remove fields|x|x|
|Cues||||
||Move, remove|x|x|
||Add |x||
|Charts||||
||Move, remove|x|x|
||Add|x| |
|Ribbon and actions||x||
|Navigation Pane||x||

Another important difference is that when personalizing by using the [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)], you can have various personalization versions of the same page, based on different access points to the page. For example, the **Sales Orders** page personalized to look different when it is opened from the **Customer Card** page than when it is opened from the **Sales Order Processor Role Center** page. When you personalize a page by using the [!INCLUDE[nav_web_md](includes/nav_web_md.md)], there is only one personalization version per page, so the changes will be seen in the page no matter you open it from.   

##  <a name="PersonalizationWinWeb"></a> Working with personalization between the Dynamics NAV Windows and Web client
Before you start personalizing pages, it is important to understand how the personalization between the [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)] and [!INCLUDE[nav_web_md](includes/nav_web_md.md)] works. If you will only ever use either the Windows client or the Web client, this information is not so relevant. However, it becomes important if and when you begin to personalize pages using both clients.  

-   If you use the [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)] to personalize a specific page for the first time, you will also see the personalization changes to the page in the [!INCLUDE[nav_web_md](includes/nav_web_md.md)] as well.

-   As long as you continue to use the [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)] to personalize the page, any personalization changes you make, will also take effect on the page in the Web client.

-   However, as soon as you start to personalize the page by using the Web client, the personalization for that page becomes separate between the two clients. In the Web client, the previous personalizations on the page are cleared, which means that the page will return to its original layout, and you will essentially start personalizing the page from scratch. The previous personalizations in the Windows client are unchanged.

- From this point on, you will personalize the page in the Windows and Web client independent of each other, which means the page can potentially look different in each client. The [!INCLUDE[nav_phone_md](includes/nav_phone_md.md)] and [!INCLUDE[nav_web_md](includes/nav_phone_md.md)] will show the same page personalizations as the Web client.  

## See Also
[Personalizing Your Workspace in the Dynamics NAV Web Client](ui-personalization-user.md)  
[Personalizing Your Workspace in the Dynamics NAV Windows Client](https://msdn.microsoft.com/en-us/library/hh879078(v=nav.90).aspx)  
[Managing Personalization](ui-personalization-manage.md)  

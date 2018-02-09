---
title: Why Can't I Personalize a Page | Microsoft Docs
description: Explains why you cannot personlaize a page and what yoo can do to unlock it so you can personalize it.
author: jswymer

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customize, personalize, personalization, hide columns, remove fields, move fields
ms.date: 09/07/2017
ms.author: jswymer

---
[!INCLUDE[personalization_md](includes/personalization_md.md)]
# Why is the page is locked from personalizing?
If there is a lock icon in the **Personalizing** banner when you open a page (as shown), this means that you are currently prevented from making any more personalization changes to the page in the [!INCLUDE[nav_web](includes/nav_web_md.md)].

![Personalize Lock](media/personalization-locked.png "Personalize lock")

There can be two reasons for this:
1.  Until now, you have only used the [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)] to personalize the page.

    or

2. You have used the [!INCLUDE[nav_web](includes/nav_web_md.md)] to personalize the page before, but it was done using a [!INCLUDE[nav2017](includes/nav2017.md)] or earlier version.   

If you want to continue personalizing the page by using the [!INCLUDE[nav_web](includes/nav_web_md.md)], choose the lock icon and then **Unlock**.

## What happens when you unlock the page
If you choose to unlock the page, the current personalization of the page in the [!INCLUDE[nav_web](includes/nav_web_md.md)] will be cleared, meaning the page will go back to its original layout and you will have to start from scratch.

In the [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)], the page will remain as was before and will not be effected by the new changes in the [!INCLUDE[nav_web](includes/nav_web_md.md)]. The page personalization in the [!INCLUDE[nav_web](includes/nav_web_md.md)] and [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)] becomes separated, where you will have a personalized version in each client. 

In the future, you will personalize the page in the two clients separately. Therefore, the page can potentially look different between the two. For more information,see [Working with personalization between the Dynamics NAV Windows and Web client](ui-personalization-overview.md#PersonalizationWinWeb).

## See Also
[Personalization Overview](ui-personalization-overview.md)  
[Personalizing Your Workspace by Using the Web Client](ui-personalization-user.md)  
[Personalizing Your Workspace by Using the Windows Client](https://msdn.microsoft.com/en-us/library/hh879078(v=nav.90).aspx)  
[Managing Personalization](ui-personalization-manage.md)  

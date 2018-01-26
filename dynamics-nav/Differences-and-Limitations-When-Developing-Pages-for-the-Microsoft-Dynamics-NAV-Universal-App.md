---
title: "Differences and Limitations When Developing Pages for the Microsoft Dynamics NAV Universal App"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: c84d915f-b845-4211-8f76-3323fd82ace5
caps.latest.revision: 28
manager: edupont
---
# Differences and Limitations When Developing Pages for the Microsoft Dynamics NAV Universal App
Developing for the [!INCLUDE[nav_tablet](includes/nav_tablet_md.md)] and [!INCLUDE[nav_phone](includes/nav_phone_md.md)] is not much different from developing for the [!INCLUDE[nav_windows](includes/nav_windows_md.md)], or [!INCLUDE[nav_web](includes/nav_web_md.md)]. There are, however, some natural limitations on tablets and phones, such as not having a physical keyboard and mouse, as well as a smaller screen. In addition to this, there are some differences and limitations in developing pages for [!INCLUDE[nav_tablet](includes/nav_tablet_md.md)] and [!INCLUDE[nav_phone](includes/nav_phone_md.md)]. The differences and limitations listed are additional to the differences and limitations that exist on the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] and [!INCLUDE[nav_web](includes/nav_web_md.md)].  

## Differences and Limitations Overview  
 The following table describes some of the most common differences and limitations that you might experience when developing for [!INCLUDE[nav_tablet](includes/nav_tablet_md.md)] and [!INCLUDE[nav_phone](includes/nav_phone_md.md)].  

|Concept|On Tablet|On Phone|Example|Recommendation/Remarks|  
|-------------|---------------|--------------|-------------|--------------------|  
|Activity buttons|Only the Home activity button is shown.|Only the Home activity button is shown.|**Home**, **Departments**, and **Posted Documents** on the Sales Order Processor Role Center.|Design pages to expose the workflows needed by the user. For example, configure the profile to show the important list pages under the Home activity button. Alternatively, consider designing a new Role Center if the activities for the activity button greatly vary from activities in other activity buttons.|  
|Selecting multiple records in lists|Not available.|Not available.|Ctrl+A or Ctrl+Click on rows in a list using [!INCLUDE[nav_windows](includes/nav_windows_md.md)].|Avoid scenarios requiring selecting multiple rows on a list. Also, try to minimize actions on lists.|  
|Ribbon actions|Only Promoted actions are shown.|Only Promoted actions are shown.|On the Small Business Role Center.|Use the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)] to promote actions. Alternatively, configure the profile and add actions to the Home ribbon tab.|  
|FactBoxes|Not shown on List pages or Worksheet pages.|Not shown on List pages or Worksheet pages.|Customer list on the Small Business Role Center.|Make sure the same information is visible on the corresponding card page of the given record.|  
|Advanced filters|No column-specific filtering is available.|No column-specific filtering is available.|On the Customer list page.|Send data to Excel and do the complex filtering there.|  
|Page search|Not available.|Not available.|On [!INCLUDE[nav_windows](includes/nav_windows_md.md)] or [!INCLUDE[nav_web](includes/nav_web_md.md)].|Design pages to expose the workflows needed by the user. For example via list places, tiles or actions.|  
|Cue and action tiles|The number of tiles that are shown is based on the size of the screen, no possibility to scroll.|The number of tiles on the phone is in theory unlimited because you can scroll.|On most Role Center pages.|Design Role Center pages to avoid having important tiles at the area end. Assume you have no control over how many tiles are displayed and consider that only the first few tiles will be made visible on the tablet.|  
|Fields in fast tabs|Fields in fast tabs on list pages are not shown. Only the repeater control is shown in the content area of the page.|Not available.||Design List pages to avoid having important columns on the far right of the column list. Assume you have no control over how many columns are displayed and consider that only the first few columns will be made visible.|  
|Links and Notes|Not available.|Not available.|On Sales Orders.|Similar to Factboxes, make sure the same information in the field group is visible on the corresponding card page of the given record.|  
|Select from full list|Not available on lookups. Users are not able to run actions on a lookup page, and they cannot access the full set of records.|Not available on lookups. Users are not able to run actions on a lookup page, and they cannot access the full set of records.|On the **Item Card** when selecting the **Base Units of Measure**.|Make sure the appropriate columns are visible on the lookup. The user is still able to filter, scroll, and search through the lookup.|  
|Search across list columns|Partly supported. Search will not include FlowFields.|Partly supported. Search will not include FlowFields.|On the Customer list page.||  
|Lookups|Available.|Available, with the difference that advanced and simple lookups behave similarly on the phone. The lookup will not bring up the card, show factboxes, or any field groups.|See examples on the Customer Card page.||  
|Matrix controls|Not available.|Not available.|See example in G/L Budget.||  
|File download|Available. Cannot download multiple files at the same time.|Available. Cannot download multiple files at the same time.|Trial Balance report in the **Print to Excel** check box.||  
|Worksheet pages|Available.|Not available; an error message is displayed.|Sales Price Worksheet or Cash Flow Worksheet.|Run this type of page from the [!INCLUDE[nav_windows](includes/nav_windows_md.md)], [!INCLUDE[nav_web](includes/nav_web_md.md)], or [!INCLUDE[nav_tablet](includes/nav_tablet_md.md)].|  
|Lists|Available.|Available, with the difference that these are displayed in a brick layout with a number of differences and limitations. For an overview, see [How to: Display Data as Bricks](How-to--Display-Data-as-Bricks.md).|Customers or Sales Orders pages.||  
|Indentation in repeater controls|Available.|Not available. The repeater control will be rendered as a regular flat brick layout.|Chart of Accounts and Contacts List pages.||  
|Scope of actions|Available.|Available, but there are some behavioral differences regarding the [Scope Property](Scope-Property.md). Also, see [Defining Action Scope for Microsoft Dynamics NAV Pages](Defining-Action-Scope-for-Microsoft-Dynamics-NAV-Pages.md).|||  
|Use of camera and location|Available in the [!INCLUDE[nav_uni_app](includes/nav_uni_app_md.md)] on devices with a camera and GPS capabilities.<br /><br /> **NOTE:** Not available on [!INCLUDE[nav_windows](includes/nav_windows_md.md)] or [!INCLUDE[nav_web](includes/nav_web_md.md)].|Available in the [!INCLUDE[nav_uni_app](includes/nav_uni_app_md.md)] on devices with a camera and GPS capabilities.<br /><br /> **NOTE:** Not available on [!INCLUDE[nav_windows](includes/nav_windows_md.md)] or [!INCLUDE[nav_web](includes/nav_web_md.md)].|On the Accounting Manager profile, under **Incoming Documents**.||  
|Use of camera and location|Available in the [!INCLUDE[nav_uni_app](includes/nav_uni_app_md.md)] on devices with a camera and GPS capabilities.<br /><br /> **NOTE:** Not available on [!INCLUDE[nav_windows](includes/nav_windows_md.md)] or [!INCLUDE[nav_web](includes/nav_web_md.md)].|Available in the [!INCLUDE[nav_uni_app](includes/nav_uni_app_md.md)] on devices with a camera and GPS capabilities.<br /><br /> **NOTE:** Not available on [!INCLUDE[nav_windows](includes/nav_windows_md.md)] or [!INCLUDE[nav_web](includes/nav_web_md.md)].|On the Accounting Manager profile, under **Incoming Documents**.||
|Automatic input focus on first editable field of a page|Not available. |Not available.|**Customer** card page.<BR /><BR />In the Windows or Web client, focus will automatically be on the first editable field (such as the **Name** field), enabling you to change the value right away.<BR /><BR />In the Tablet or Phone client, this field will not be in focus; instead, you will have to manually select the field first in order to make changes.| The reason for this behavior is to prevent the in-app keyboard from initially displaying and occupying screen space.|   

## See Also  
 [Developing for the Microsoft Dynamics NAV Universal App](Developing-for-the-Microsoft-Dynamics-NAV-Universal-App.md)   
 [Developing for the Microsoft Dynamics NAV Web Client](Developing-for-the-Microsoft-Dynamics-NAV-Web-Client.md)   
 [Role Center Behaviors](Role-Center-Behaviors.md)   
 [How to: Display Data as Bricks](How-to--Display-Data-as-Bricks.md)   
 [How to: Implement the Camera in C/AL](How-to--Implement-the-Camera-in-C-AL.md)   
 [How to: Implement Location in C/AL](How-to--Implement-Location-in-C-AL.md)

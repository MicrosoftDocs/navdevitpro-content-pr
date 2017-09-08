---
title: Personalizing Pages in the Dynamics Windows Client| Microsoft Docs
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
# Personalizing Your Workspace in the Dynamics Windows Client
You can personalize your workspace to suit your work and preferences by changing pages so that they display only the information you need, where you need it. The personalization changes that you make will only affect what you see, not what other users see. You can personalize many parts of the user interface, including which actions to include on the ribbon, how fields are positioned on FastTabs or in FactBoxes, and which menu items to include in the navigation pane. You perform this work in the Customize window, which you can open from practically all types of pages.

You can record multiple customizations of the same page based on different access points to the page. For example, the Sales Orders window can be customized to look different when it is opened from the Customer Card window than when it is opened from the Sales Order Processor Role Center. The point from which you access the page to be customized is recorded in that specific page customization. Accordingly, there may be multiple page-customization records in the database, as you can see in the ($ N_9191 Delete User Personalization $) window.

You can cancel UI customization that you have made, either for a specific area on a page, such as a ribbon, or for the whole page. Your page layout is then reset to the default user interface for your profile.

In addition to UI customization that you perform in the Customize window, you can make basic changes of your view of the UI. You can adjust the size and position of any window, expand the width of columns and increase the height of column headers, and change the sorting of data in columns. You also perform a type of personalization, when you select default options on dialog boxes that you are presented with when Microsoft Dynamics NAV receives external files or must run automation objects. You can cancel such basic UI changes and default settings for handling files and automation objects with different functions than those for canceling UI customizations.

> [!NOTE]  
> You can also personalize pages by using the [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)]. To learn how personalization works between the [!INCLUDE[nav_windows_md](includes/nav_windows_md.md)] and [!INCLUDE[nav_web_md](includes/nav_web_md.md)], see [Personalizing Your Workspace](ui-personalization-overview.md).

The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.

To See 
Change which actions to show on the ribbon and how the actions are grouped.
 How to: Customize Ribbons
 
Change which FastTabs to show and which fields to include on the FastTabs.
 How to: Customize FastTabs
 
Change which FactBoxes to show and which fields to include in FactBoxes.
 How to: Customize FactBoxes
 
Specify if you want to always display the filter pane at the top of a list page and document page and if you always want to show FactBoxes on a page.
 How to: Add or Remove Filter Panes and FactBox Panes
 
Add, remove, or change the order of list or document-line columns that represent fields in the underlying tables.
 How to: Add or Remove Columns in a List or on Document Lines
 
Define a divider on the horizontal layout of columns in front of which columns do not move when you scroll horizontally.
 How to: Add Freeze Panes
 
Rename or rearrange buttons, create a new menu button, add a link to a menu, or rearrange the order of a menu.
 How to: Customize the Navigation Pane
 
Add a link from a department page to your Role Center.
 How to: Add Department Links to the Role Center
 
Add a chart to your Role Center or to a list page.
 How to: Add Charts to Role Centers and List Pages
 
Cancel customization that you have made to your user interface, either for a specific area on a page, such as a ribbon, or for the whole page.
 How to: Cancel UI Personalization
 
Adjust the size and position of windows and columns by dragging, increase the height of column headers, and change the sorting of data in columns.
 How to: Make Basic UI Changes

 
Select default options on dialog boxes that you are presented with when Microsoft Dynamics NAV receives external files or must run automation objects.
 How to: Specify How to Handle External Files and Automation Objects
 
Undo basic UI changes and default settings for handling files and automation objects.
 How to: Cancel Basic UI Changes and File Handling Decisions
 

## See Also
[Personalizing Your Workspace in the Dynamics NAV Web Client](ui-personalize-user-interface.md)  
[Managing Personalization](ui-manage-personalization.md)  
[Customizing the User Interface](customizing-the-user-interface.md)  

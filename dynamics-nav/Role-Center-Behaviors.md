---
title: Role Center Behaviors
description: This article describes how the behavior has influence in the tablet client and phone client than the windows client and the web client.
ms.custom: na
ms.date: 10/23/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 04cff7a2-2d36-4975-be75-efa052da348b
caps.latest.revision: 11
---
# Role Center Behaviors
This section describes in which areas the Role Center pages have a different behavior in the [!INCLUDE[nav_tablet](includes/nav_tablet_md.md)] and the [!INCLUDE[nav_phone](includes/nav_phone_md.md)] than in the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] and the [!INCLUDE[nav_web](includes/nav_web_md.md)]. This behavior has influence on how you will build your Role Center pages. For information about pages on tablets and phones in general, see [Differences and Limitations When Developing Pages for the Microsoft Dynamics NAV Universal App](Differences-and-Limitations-When-Developing-Pages-for-the-Microsoft-Dynamics-NAV-Universal-App.md).  
  
## Behavioral Differences  
  
|Concept|On Tablet/Phone|  
|-------------|----------------------|  
|Tiles|The app bar will automatically show tiles in two or three columns depending on the total number of tiles. A Role Center with many tiles only displays the tiles that fit vertically on the screen; other tiles are not shown and will not be available.<br /><br /> On the phone, the Home page will automatically show tiles in one or two columns depending on the total number of tiles and these can be scrolled.|  
|Actions|Actions that are added under an **ActionContainer** of the subtype **HomeItems** are always shown in the navigation pane.|  
|Actions|Actions that are added under an **ActionContainer** of the subtype **ActivityButtons** are never shown, and cannot be accessed.<br /><br /> There is no ability to navigate to other Activity Buttons as you can do in [!INCLUDE[nav_windows](includes/nav_windows_md.md)] and [!INCLUDE[nav_web](includes/nav_web_md.md)]. Because Activity Buttons link to related functionality, the recommended workaround is to providing links to this functionality through their own Role Center as a separate entry point.|  
|Actions|-   In the action pane, if the current profile has no configuration for the specific page, for example, if this was deleted, only promoted actions will be shown. If there are no promoted actions, any actions under **NewDocumentItems** will be shown. If there are no **NewDocumentItems** actions, an empty pane will be shown.<br />-   If a page configuration exists, the **NewDocumentItems** will be shown, together with any new groups that were created. Actions, even if they were renamed, which remain in their original group will not show until you move them to a custom group. This behavior differs from [!INCLUDE[nav_windows](includes/nav_windows_md.md)] which will always show them.<br />-   When you add actions to the **Home** tab, it corresponds to setting the actions to **Promoted**. However, you can only do this with the configuration tooling if there is at least one **Promoted** action. Otherwise, the **Home** tab will never be available for customization.|  
|Parts|Available on the tablet.<br /><br /> On the phone, there is a limit to a total number of 5 parts that can be displayed. If you have multiple parts that contain cues, these are currently displayed as one part.<br /><br /> When building Role Centers it is recommended to avoid using the **Group** type to group the parts that make up the Role Center, and instead create all parts directly underneath the **Container** type. This will optimize the layout to dynamically switch from a 1 to 2 to 3 column layout and thereby fit more display targets.|  
  
## See Also  
 [Developing for the Microsoft Dynamics NAV Universal App](Developing-for-the-Microsoft-Dynamics-NAV-Universal-App.md)   
 [Differences and Limitations When Developing Pages for the Microsoft Dynamics NAV Universal App](Differences-and-Limitations-When-Developing-Pages-for-the-Microsoft-Dynamics-NAV-Universal-App.md)
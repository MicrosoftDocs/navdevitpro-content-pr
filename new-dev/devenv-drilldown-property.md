---
title: "DrillDown Property"
ms.custom: na
ms.date: 05/10/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: de4f0602-ddd3-43b1-9f3d-8e62368c08de
caps.latest.revision: 15
manager: edupont
---
# DrillDown Property
Sets a drill-down for a field on a page.  
  
## Applies To  
  
-   Page Fields  
  
> [!IMPORTANT]  
>  This property is not supported on Repeater controls on pages when it is displayed in the [!INCLUDE[nav_web](includes/nav_web_md.md)].  
  
## Property Value  
 **true** if a drill-down for the field is provided; otherwise, **false**. The default value is **false**.  
  
## Remarks  
 Drill-downs are a system-wide feature of [FlowFields](FlowFields.md) that let you see the underlying transactions that make up the information shown in the FlowField. For example, if the FlowField shows an account balance, then providing a drill-down for this text box lets the user quickly see the various transactions that make up the balance shown in the field.  
  
## See Also  
 [Pages](Pages.md)   
 [Page Properties](Page-Properties.md)   
 [Page Properties Not Supported by Microsoft Dynamics NAV Web Client](Page-Properties-Not-Supported-by-Microsoft-Dynamics-NAV-Web-Client.md)
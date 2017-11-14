---
title: "OnDrillDown Trigger"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-financials"
ms.assetid: a25a1651-d138-497c-8dab-34bdf38ee17a
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# OnDrillDown Trigger
Overrides the default drill-down behavior defined in the table definition for the FlowField.  

## Applies To  
 Fields on pages  

> [!NOTE]  
>  The OnDrillDown trigger is not invoked on fields in a Repeater control<!--NAV in the [!INCLUDE[nav_web](../includes/nav_web_md.md)]-->.  

## Remarks  
 If there is an error in the trigger code, the drilldown is canceled. You can use this trigger to write to the database.  

 This trigger overrides the [DrillDownPageID Property](../properties/devenv-drilldownpageid-property.md) setting of the FlowField.  

## See Also  
 [Triggers](devenv-triggers.md)  
 [DrillDownPageID Property](../properties/devenv-drilldownpageid-property.md)  
 [Page and Action Triggers](devenv-page-and-action-triggers.md)  
 [Page Properties](../properties/devenv-page-properties.md)  

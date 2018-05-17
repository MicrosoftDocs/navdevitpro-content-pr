---
title: "AssistEdit Property"
ms.custom: na
ms.date: 06/09/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: dd671414-a7c3-44bd-a860-a8bda61c7913
caps.latest.revision: 15
author: SusanneWindfeldPedersen
redirect_url: /dynamics365/business-central/dev-itpro/developer/properties/devenv-properties
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# AssistEdit Property
Sets assist-edit capabilities for a text box.  
  
## Applies To  
  
-   Page Fields  
  
## Property Value  
 **True** if assist-edit capabilities and an AssistEdit button are provided; otherwise, **false**. The default value is **false**.  
  
## Remarks  
 You can add AL code in the [OnAssistEdit Trigger](../triggers/devenv-onassistedit-trigger.md) to change the default assist-edit behavior.  
  
 <!-- //NAV
 In the [!INCLUDE[nav_web](includes/nav_web_md.md)], the AssistEdit button does not appear on the field when the page is in the view mode or if the field has the data type of Option.  
 --> 
## See Also  
 [Lookup Property](devenv-lookup-property.md)   
 [DrillDown Property](devenv-drilldown-property.md)
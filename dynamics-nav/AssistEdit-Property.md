---
title: "AssistEdit Property"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: dd671414-a7c3-44bd-a860-a8bda61c7913
caps.latest.revision: 15
manager: terryaus
---
# AssistEdit Property
Sets assist\-edit capabilities for a text box.  
  
## Applies To  
  
-   Page Fields  
  
## Property Value  
 **Yes** if assist\-edit capabilities and an AssistEdit button are provided; otherwise, **No**. The default value is **No**.  
  
## Remarks  
 You can add C\/AL code in the [OnAssistEdit Trigger](OnAssistEdit-Trigger.md) to change the default assist\-edit behavior.  
  
 In the [!INCLUDE[nav_web](includes/nav_web_md.md)], the AssistEdit button does not appear on the field when the page is in the view mode or if the field has the data type of Option.  
  
## See Also  
 [Lookup Property](Lookup-Property.md)   
 [DrillDown Property](DrillDown-Property.md)
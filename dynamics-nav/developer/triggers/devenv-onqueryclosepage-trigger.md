---
title: "OnQueryClosePage Trigger"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-financials"
ms.assetid: 820616a5-daa7-4819-8bf8-02f376ef806e
author: SusanneWindfeldPedersen
manager: edupont
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# OnQueryClosePage Trigger
Executed as a page closes and before the [OnClosePage Trigger](devenv-OnClosePage-Trigger.md) executes.  

## Syntax  

```  

[Ok]:= OnQueryClosePage(CloseAction)  
```  

#### Parameters  
 *CloseAction*  

 (Action) The *CloseAction* chosen by the user; usually OK or Cancel.  

## Return Value  
 *Ok*  
 Type: Boolean  

 **True** to close the page; otherwise **false**. This value is checked after each  call.  

## Applies To  

-   Pages  

<!--NAV  
> [!IMPORTANT]  
>  The OnQueryClosePage trigger is not fully supported by the [!INCLUDE[nav_web](../includes/nav_web_md.md)]. When the page displays in the [!INCLUDE[nav_web](../includes/nav_web_md.md)], the trigger is only invoked when the page is hosted in a modal popup window \(MPO\).  
-->  

> [!IMPORTANT]  
>  The trigger is only invoked when the page is hosted in a modal popup window \(MPO\).  

## Remarks  
 If the page that is closing and all its child pages return **true** in the OnQueryClosePage trigger, then the [OnClosePage Trigger](devenv-onclosepage-trigger.md) is called for all child pages and then for the parent page.  

 If an error occurs in the OnQueryClosePage trigger or it returns **false**, then the page is not closed.  

 When the OnQueryClosePage trigger is called on a subpage, the *CloseAction* parameter is set to the same value as the parent page.  

 You can use this trigger to write to the database.

 ## See Also  
 [OnClosePage Trigger](devenv-onclosepage-trigger.md)  
 [Page and Action Triggers](devenv-page-and-action-triggers.md)  
 [Page Properties](../properties/devenv-page-properties.md)  
 [Triggers](devenv-triggers.md)  


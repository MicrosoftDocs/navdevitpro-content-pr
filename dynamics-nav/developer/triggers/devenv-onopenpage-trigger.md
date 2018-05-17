---
title: "OnOpenPage Trigger"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-financials"
ms.assetid: c6b911c1-55b2-4837-b1af-32dbe64f84e3
author: SusanneWindfeldPedersen
manager: edupont
redirect_url: /dynamics365/business-central/dev-itpro/developer/triggers/devenv-triggers
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# OnOpenPage Trigger
Executed after a page is initialized and run.  

## Syntax  

```  

OnOpenPage()  
```  

## Applies To  

-   Pages  

## Remarks  
 This trigger is executed after the [OnInit Trigger](devenv-oninit-trigger.md).  

 You use the OnOpenPage trigger to change dynamic properties, including those which can only be changed when the page is opened, such as the [Visible Property](../properties/devenv-visible-property.md). You can also write to the database from the trigger.  

 The `OnOpenPage` trigger is the only trigger that can toggle the [Visible Property](../properties/devenv-visible-property.md) and the property can only be toggled on columns. 

 If an error occurs in the trigger execution, then the page closes.  

> [!NOTE]  
>  If you use the [LOCKTABLE Record)](../methods/devenv-locktable-method-record.md) in the OnOpenPage trigger, then the table lock will be released when the trigger completes execution and not when the user closes the page.  

> [!NOTE]  
>  The OnOpenPage trigger does not support calls to control add-in methods and properties because the trigger is invoked before the page is instantiated. <!-- For more information see, [Exposing Methods and Properties in a Windows Client Control Add-in](exposing-methods-and-properties-in-a-windows-client-control-add-in.md).-->

## See Also  
 [Triggers](devenv-triggers.md)  
 [Page and Action Triggers](devenv-page-and-action-triggers.md)  
 [LOCKTABLE Record](../methods/devenv-locktable-method-record.md)  
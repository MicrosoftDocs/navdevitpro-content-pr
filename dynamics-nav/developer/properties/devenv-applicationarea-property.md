---
title: "ApplicationArea Property"
ms.custom: na
ms.date: 06/09/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# ApplicationArea Property
Sets the application areas that apply to the control.  
  
## Applies to  
  
-   Page field, part, and action controls 
  
-   Report request page field controls  
  
-   MenuSuite items  
  
## Property Values  
 A text string that contains a comma-separated list of application area tags.  
  
 An application area tag must have the format #*name*, where *name* is the application area. The *name* can be any combination of letters (Aa-Zz) and numbers (0-9) without spaces. For example, to specify the **Basic** and **Fixed Assets** application areas, set the property to **#Basic,#FixedAssets**.  
  
 If the control applies to all application areas, you can set the property to **#All**. This means that the control will always appear in the user interface.  
  
## Remarks  
 This property is used together with the APPLICATIONAREA method to hide user interface elements.  
  
 If one or more application areas are enabled in a session, any controls that are not tagged with an application area will not appear in the user interface.  
   
## See Also  
 [APPLICATIONAREA Method](../methods/devenv-applicationarea-method.md)
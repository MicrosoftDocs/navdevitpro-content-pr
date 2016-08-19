---
title: "ApplicationArea Property"
ms.custom: na
ms.date: 06/04/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: ee665b86-d582-4d4e-8e7b-b28b4d392801
caps.latest.revision: 5
manager: edupont
---
# ApplicationArea Property
Sets the application areas that apply to the control.  
  
## Applies to  
  
-   Page field, part, and action controls.  
  
-   Report request page field controls.  
  
-   MenuSuite items  
  
## Property Values  
 A text string that contains a comma\-separated list of application area tags.  
  
 An application area tag must have the format \#*name*, where *name* is the application area. The *name* can be any combination of letters \(Aa\-Zz\) and numbers \(0\-9\) without spaces. For example, to specify the **Foundation** and **Fixed Assets** application areas, set the property to **\#Foundation,\#FixedAssets**.  
  
 If the control applies to all application areas, you can set the property to **\#All**. This means that the control will always appear in the user interface.  
  
## Remarks  
 This property is used together with the APPLICATIONAREA function to hide user interface elements based on the application area.  
  
 If one or more application areas are enabled in a session, any controls that are not tagged with an application area will not appear in the user interface.  
  
 You can get an overview of the application areas that are tagged on all controls of an object by displaying the **ApplicationArea** column in the designer.  
  
> [!NOTE]  
>  Currently, this property is intended for the application areas that are defined in **table 9178 Application Ares Setup**. You can define your own application areas but the implementation might change in future release.  
  
## See Also  
 [APPLICATIONAREA Function](APPLICATIONAREA-Function.md)
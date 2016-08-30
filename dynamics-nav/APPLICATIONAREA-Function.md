---
title: "APPLICATIONAREA Function"
ms.custom: na
ms.date: 06/04/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: f0428b42-0352-4298-8299-dcc1de1809e1
caps.latest.revision: 4
manager: edupont
---
# APPLICATIONAREA Function
Gets or sets the application areas for the current session.  
  
## Syntax  
  
```  
[ApplicationArea :=] APPLICATIONAREA([ApplicationArea])  
```  
  
#### Parameters  
 *ApplicationAreas*  
 Type: Text  
  
 A comma-separated list of application area tags to activate.  
  
 An application area tag has the format \#*name*, where *name* is the application area. The *name* can be any combination of letters \(Aa-Zz\) and numbers \(0-9\) without spaces. For example, to specify the **Foundation** and **Fixed Assets** application areas, set the property to **\#Foundation,\#FixedAssets**.  
  
## Property Value/Return Value  
 Type: Text  
  
 A comma-separated list of enabled application areas for the current session.  
  
## Remarks  
 This function lets  you to hide certain user interface elements \(including page fields and actions, report request page options, and Department items\) based on the application area to which they belong. Controls that define these items can be are tagged with one or more application areas by setting the ApplicationArea property. When the APPLICATIONAREA function is called for a client session, only those controls that are tagged with the application areas set by the function will be appear in the user interface.  
  
> [!NOTE]  
>  Currently, this functionality is intended for the application areas that are defined in **table 9178 Application Ares Setup**. You can define your own application areas but the implementation might change in future release.  
  
## See Also  
 [ApplicationArea Property](ApplicationArea-Property.md)
---
title: "CURRENTDATETIME Method (DateTime)"
ms.custom: na
ms.date: 06/04/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: dynamics365-financials
ms.assetid: 722ef035-cc46-4948-b4d7-0604a8ba11f9
caps.latest.revision: 7
manager: edupont
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# CURRENTDATETIME Method (DateTime)
Gets the current DateTime.  
  
## Syntax  
  
```  
  
DateTime := CURRENTDATETIME  
```  
  
## Property Value/Return Value  
 Type: DateTime  
  
 The current DateTime.  
  
## Example  
 This example requires that you create a DateTime variable named TestDateTime.  
  
```  
TestDateTime := CURRENTDATETIME;  
MESSAGE(Format(TestDateTime));  
```  
  
 The message window displays the current date and time.  
  
## See Also  
 [DateTime Methods](devenv-DateTime-Methods.md)
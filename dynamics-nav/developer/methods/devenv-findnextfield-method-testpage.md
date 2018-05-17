---
title: "FINDNEXTFIELD Method (TestPage)"
ms.custom: na
ms.date: 07/13/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: dynamics365-financials
ms.assetid: 1d759dae-b951-4441-bffb-8db2047f0872
caps.latest.revision: 5
redirect_url: /dynamics365/business-central/dev-itpro/developer/methods/devenv-al-method-reference
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# FINDNEXTFIELD Method (TestPage)
Finds the next field in the dataset that is displayed on a test page.  
  
## Syntax  
  
```  
[Ok :=]TestPage.FINDNEXTFIELD(Field, Value);  
```  
  
#### Parameters  
 TestPage  
 Type: TestPage  
  
 The test page that contains the dataset that you want to find.  
  
 *Field*  
 Type: Field  
  
 The field to find.  
  
 *Value*  
 Type: Any  
  
 The value of the field.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 **true** if the first field is found; otherwise, **false**. The return value is optional.  
  
## See Also  
 [TestPage Methods](devenv-TestPage-Methods.md)
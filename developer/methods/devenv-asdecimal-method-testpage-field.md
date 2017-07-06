---
title: "ASDECIMAL Method (TestPage Field)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-for-financials"
ms.assetid: 05375a96-3aa0-41e2-a141-99dcacff37dc
caps.latest.revision: 4
manager: edupont
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# ASDECIMAL Method (TestPage Field)
Converts the value in a field on a test page to a **DECIMAL** data type.  
  
## Syntax  
  
```  
Decimal := TestPage.Field.ASDECIMAL  
```  
  
#### Parameters  
 *TestPage*  
 Type: TestPage  
  
 The test page variable that you use to refer to the test page.  
  
 *Field*  
 Type: Field  
  
 The field that contains the value that you want to convert.  
  
## Property Value/Return Value  
 Type: Decimal  
  
 The converted value.  
  
## See Also  
 [TestPage Field Methods](devenv-TestPage-Field-Methods.md)
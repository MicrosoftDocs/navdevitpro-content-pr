---
title: "ValuesAllowed Property"
ms.custom: na
ms.date: 06/16/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 38807291-9e71-4a10-8c5a-e4f011061f1e
caps.latest.revision: 11
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# ValuesAllowed Property
Sets the values that are allowed in the field.  
  
## Applies To  
  
-   Table Fields  
  
-   Page Fields  
  
## Remarks  
 Separate the values with a semicolon. For example, if you only want the user to enter 1, 3, or 5 in this field, enter 1;3;5 for this property.  
  
 The property setting is checked during validation. Validation occurs only if the field or control value is updated through the UI, for example, if a value is updated on a page or if a field is updated in a table. If a field is updated through application code, then the **ValuesAllowed** property is not validated.  
  
## See Also  
 [Properties](devenv-properties.md)
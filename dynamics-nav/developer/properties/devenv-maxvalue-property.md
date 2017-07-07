---
title: "MaxValue Property"
ms.custom: na
ms.date: 06/16/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: f4d4594a-ef77-4f13-989f-28912b82a3d4
caps.latest.revision: 12
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# MaxValue Property
Sets the maximum numeric value for a field.  
  
## Applies To  
  
-   Page Fields  
  
## Property Value  
  
|**Value**|**Description**|  
|---------|---------------|  
|**9999**|Integers|  
|**9999.0**|Decimals|  
|**December 31, 9999**|Dates|  
|**23:59:59**|Time|  
  
## Remarks  
 The field setting is checked during validation. Validation occurs only if the field or control value is updated through the UI, for example, if a value is updated on a page or if a field is updated in a table directly. If a field is updated through application code, then the **MaxValue** is not validated.  
  
## See Also  
 [MinValue Property](devenv-minvalue-property.md)   
 [NotBlank Property](devenv-notblank-property.md)   
 [Numeric Property](devenv-numeric-property.md)
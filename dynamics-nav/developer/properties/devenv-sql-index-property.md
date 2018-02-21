---
title: "SQLIndex Property"
ms.custom: na
ms.date: 06/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 58a94a2c-fbdd-404e-9760-9bfede48f36e
caps.latest.revision: 5
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# SQLIndex Property
Sets the actual fields that are used in the corresponding index on SQL Server.  
  
## Applies To  
 Keys  
  
## Remarks  
 This property allows you to define the fields that are used in the SQL index.  
  
 The fields in the SQL index can:  
  
-   Differ in number from the fields defined in the key in Microsoft Dynamics NAV—there can be fewer fields or more fields.  
  
-   Be arranged in a different order.  
  
 If you use this property to define an index on a key that is not the primary key, then the index that is created contains exactly the fields that you specify and will not be a unique index. A unique index will only be created if it contains all of the primary key fields.  
  
 If you use this property to define an index for the primary key, it must include all the fields defined in the primary key. You can add extra fields and you can rearrange the fields to suit your needs.  
 <!--  
## See Also  
 [How to: Define Primary and Secondary Keys](How-to--Define-Primary-and-Secondary-Keys.md) -->
---
title: "PreserveWhiteSpace Property"
ms.custom: na
ms.date: 06/14/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 0df27817-0c01-4df4-b645-22abd1d937d0
caps.latest.revision: 8
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# PreserveWhiteSpace Property
Determines whether white space should be preserved in documents that are imported through an XMLport.  
  
 By default, [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] supports the XML standard by normalizing white space in attribute names and values that are imported through an XMLport. It converts tabs, carriage returns, and spaces to single spaces. It also eliminates leading and trailing white space.  
  
 When this property is set to **true**, no normalizations are performed.  
  
## Applies To  
 XMLports  
  
## Property Value  
 **False** to normalize white space; otherwise, **true** to not normalize white space. The default is **false**.  
  
## See Also  
 [Properties](devenv-properties.md)
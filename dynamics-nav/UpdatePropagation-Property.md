---
title: "UpdatePropagation Property"
ms.custom: na
ms.date: 05/04/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 56b70fb2-c01f-4558-89f0-f991f2a24d78
caps.latest.revision: 5
manager: edupont
---

# UpdatePropagation Property
Sets a value that specifies what happens when a main page with a subpart is updated. The **UpdatePropagation** property is available on part controls and has two options; **Subpart** and **Both**. If **UpdatePropagation** is set to **Subpart**, an update action will update the subpart only. If **UpdatePropagation** is set to **Both**, an update action will update both the main page and the subpart. This is useful if a value on the subpart changes, and you want a main page total to be refreshed automatically.  
  
## Applies to  
  
-   Page parts  
  
## Remarks  
 Use the **UpdatePropagation** property to update a main page total, when the amount on the subpart lines is updated. Add a `CurrPage.UPDATE();` call, for example, in the OnValidate trigger on the subpart to have the **UpdatePropagation** property take effect.
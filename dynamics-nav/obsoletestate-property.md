---
title: "ObsoleteState Property"
description: "Description of the ObsoleteState property"
author: jswymer
ms.custom: na
ms.date: 12/08/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: jswymer
---
# ObsoleteState Property
Marks whether the table, field, or key is will become obsolete (or deprecated) in a future release or it is already obsolete.   

## Applies To  

-   Table objects
-   Table fields
-   Table keys
  
## Property Value  
 The following table describes the property values.  

|  Value  |  Description  |
|---------|---------------|  
|**No**|Not obsolete. This is the normal/default setting.|  
|**Pending**|Will be obsolete in the future. This setting has no effect on the current use of the table, field, or key in code. |  
|**Removed**|Marked as obsolete in the database. The element is not removed from the database. However, references to the the element in code are only allowed in upgrade codeunits. References from other objects will result in a runtime error.|   

## Remarks  
By coding against this property, you can use this property as a way to communicate through code to other developers which tables and fields will become obsolete over time and those which are already obsolete, enabling them to adjust there application code accordingly.

## See Also  
 [ObsoleteReason Property](Oobsoletereason-property.md)  
 [Properties](Properties.md)  
 [Upgrade Codeunits](upgrade-codeunits.md)  


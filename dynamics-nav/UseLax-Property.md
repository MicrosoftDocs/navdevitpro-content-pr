---
title: "UseLax Property"
description: Learn how the UseLax property specifies whether an XMLport uses LAX (Lazy API for XML) to process an XML file.
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: d95f6afe-8b48-4934-be3b-0e5d0fda4aa0
caps.latest.revision: 5
manager: edupont
---
# UseLax Property
Specifies whether an XMLport uses LAX \(Lazy API for XML\) to process an XML file.  
  
## Applies To  
  
-   XMLports  
  
## Property Value  
 **Yes** if the XMLport uses LAX; otherwise **No**.  
  
## Remarks

Extra elements and attributes are often added to XML documents when they are processed in software systems. If this property is set to **Yes**, the XML document will validate as long as the document meets the minimum schema definition. This means that if extra elements and attributes are included in a namespace, the XML document will successfully validate against the schema; if not, a validation error will occur.
  
## See Also  
 [Properties](Properties.md)
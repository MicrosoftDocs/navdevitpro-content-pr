---
title: "Path Method"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 02/21/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 620f0e32-eadc-43e9-8f6e-8fc0b12c3aaf
caps.latest.revision: 9
manager: edupont
author: SusanneWindfeldPedersen
---

# Path Method

Retrieves the JSON path of the array relative to its containing tree.

```
String := JsonArray.Path
```

## Parameters
*JsonArray*  
&emsp;Type: JsonArray

## Property Value/Return Value
Type : String

The path of the array relative to its containing JSON tree.
If the object is the root of the JSON tree, the path will be empty.

## See Also
[Getting Started](newdev-get-started.md)  
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)

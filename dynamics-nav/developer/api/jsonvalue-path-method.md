---
title: "Path Method"
ms.author: solsen
ms.custom: na
ms.date: 06/30/2017
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

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# Path Method

Retrieves the JSON path of the value relative to its containing tree.

```
String := JsonValue.Path
```

## Parameters
*JsonValue*  
&emsp;Type: JsonValue

## Property Value/Return Value
Type: String

The path of the value relative to its containing JSON tree.
If the object is the root of the JSON tree, the path will be empty.

## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

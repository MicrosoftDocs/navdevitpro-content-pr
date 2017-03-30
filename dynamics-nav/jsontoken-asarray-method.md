---
title: "AsArray Method"
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

# AsArray Method

Converts the value in a JsonToken to a JsonArray data type.

```
JsonArray := JsonToken.AsArray
```

## Parameters
*JsonToken*  
&emsp;Type: JsonToken

A JsonToken for which IsArray returns **true**. If the JsonToken does not represent a JSON array, a run-time error occurs.

## Return Value
Type: JsonArray

The returned JsonArray contains the same data as the JsonToken, but allows array-specific operations to be performed on it.

## See Also
[Getting Started](newdev-get-started.md)  
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)

---
title: "AsDateTime Method"
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

# AsDateTime Method

Converts the value in a JsonValue to a DateTime data type.

```
DateTime := JsonValue.AsDateTime
```

## Parameters
*JsonValue*  
&emsp;Type: JsonValue

## Return Value
Type: DateTime

## Remarks
If the JsonValue does not contain a string of the format "o" as specified [here](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) the operation will fail with a run-time error.

If there is no timezone specifier, the value will be treated as a UTC DateTime. If the timezone specifier is local, it will be treated as local to the server's timezone and converted to UTC. We recommend using UTC time to prevent unexpected behavior.

## See Also
[Getting Started](devenv-get-started.md)  
[Developing Extensions Using the New Development Environment](devenv-dev-overview.md)

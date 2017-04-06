---
title: "IndexOf Method"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 03/28/2017
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

# IndexOf Method
Replaces the value at the given index with a new value.

```
Index := JsonArray.IndexOf(Value)
```
## Parameters
*JsonArray*  
&emsp;Type: JsonArray

*Value*  
&emsp;Type: JsonToken | sonToken | JsonObject | JsonValue | JsonArray | Boolean | Char | Byte | Integer | BigInteger | Decimal | Duration | String | Date | Time | DateTime

## Return Value
&emsp;Type: Integer

The position of the value in the JsonArray. -1 will be returned if *Value* cannot be found in the array.

## See Also
[Getting Started](newdev-get-started.md)  
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)

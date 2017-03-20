---
title: "Set Method"
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

# Set Method

Replaces the value at the given index with a new value.

```
[Ok := ] JsonArray.Set(Index, Value)
```

## Parameters
*JsonArray*
Type: JsonArray

*Index*
Type: Integer

*Value*
Type: JsonToken | JsonObject | JsonValue | JsonArray | Boolean | Char | Byte | Integer | BigInteger | Decimal | Duration | String | Date | Time | DateTime

## Return Value
Type: Boolean

**true** if the operation was successful; otherwise, **false**.
If you omit this optional return value and if the select does not execute successfully, then a run-time error occurs.

## Remarks
The operation will fail if the *Index* is smaller than 0 or (greater or equal) than JsonArray.Count.

## See Also
[Getting Started](newdev-get-started.md)  
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)

---
title: "AsValue Method"
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
author: solsen
---

# AsValue Method

Converts the value in a JsonToken to a **JsonValue** data type.

```
JsonValue := JsonToken.AsValue
```

### Parameters
*JsonToken*
Type: JsonToken

A JsonToken for which **IsValue** returns **true**. If the JsonToken does not represent a fundamental JSON value, a run-time error occurs.

## Return Value
Type : JsonValue

The returned JsonValue contains the same data as the JsonToken, but allows value-specific operations to be performed on it (the data).

## See Also

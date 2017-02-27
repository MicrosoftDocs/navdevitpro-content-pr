---
title: "IndexOf Method"
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

# IndexOf Method

Replaces the value at the given index with a new value. 

```
Index := JsonArray.IndexOf(Value)
```
## Parameters
*JsonArray*
Type: JsonArray

*Value*
Type: JsonToken | sonToken | JsonObject | JsonValue | JsonArray | Boolean | Char | Byte | Integer | BigInteger | Decimal | Duration | String | Date | Time | DateTime

## Return Value
*Index*
Type: Integer

The position of the value in the **JsonArray**. -1 will be returned if the Value cannot be found in the array.

## Remarks
//TODO: Big notice about the fact that JsonArray is 0 based.

## See Also
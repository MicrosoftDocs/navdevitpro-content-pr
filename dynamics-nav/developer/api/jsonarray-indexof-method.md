---
title: "IndexOf Method"
ms.author: solsen
ms.custom: na
ms.date: 12/15/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 620f0e32-eadc-43e9-8f6e-8fc0b12c3aaf
caps.latest.revision: 9
manager: edupont
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# IndexOf Method
Replaces the value at the given index with a new value.

```
Index := JsonArray.IndexOf(Value)
```
## Parameters
*JsonArray*  
&emsp;Type: [JsonArray](jsonarray-class.md)

*Value*  
&emsp;Type: [JsonToken](jsontoken-class.md) | [JsonObject](jsonobject-class.md) | [JsonValue](jsonvalue-class.md) | [JsonArray](jsonarray-class.md) | [Boolean](../datatypes/devenv-boolean-data-type.md) | [Char](../datatypes/devenv-char-data-type.md) | [Byte](../datatypes/devenv-byte-data-type.md) | [Integer](../datatypes/devenv-integer-data-type.md) | [BigInteger](../datatypes/devenv-biginteger-data-type.md) | [Decimal](../datatypes/devenv-decimal-data-type.md) | [Duration](../datatypes/devenv-duration-data-type.md) | [String](../datatypes/devenv-text-data-type.md) | [Date](../datatypes/devenv-date-data-type.md) | [Time](../datatypes/devenv-time-data-type.md) | [DateTime](../datatypes/devenv-datetime-data-type.md)

## Return Value
&emsp;Type: [Integer](../datatypes/devenv-integer-data-type.md)

The position of the value in the JsonArray. -1 will be returned if *Value* cannot be found in the array.

## See Also
[JsonArray](jsonarray-class.md)  
[HTTP, JSON, TextBuilder, and XML API](../devenv-restapi-overview.md)  
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

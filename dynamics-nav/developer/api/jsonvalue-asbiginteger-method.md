---
title: "AsBigInteger Method"
ms.author: solsen
ms.custom: na
ms.date: 06/29/2017
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

# AsBigInteger Method

Converts the value in a JsonValue to an BigInteger data type.

```
BigInteger := JsonValue.AsBigInteger
```

## Parameters
*JsonValue*  
&emsp;Type: [JsonValue](jsonvalue-class.md)

## Return Value
[BigInteger](../datatypes/devenv-biginteger-data-type.md)

## Remarks
If the JsonValue does not contain number or a string which can be converted without loss of precision to an BigInteger, the operation will fail with a run-time error.

## See Also
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

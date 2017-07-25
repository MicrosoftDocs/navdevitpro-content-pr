---
title: "AsOption Method"
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

# AsOption Method

Converts the value in a JsonValue to an Option data type.

```
Option := JsonValue.AsOption
```

### Parameters
*JsonValue*  
&emsp;Type: JsonValue

## Return Value
Type: Option

## Remarks
If the JsonValue does not contain a number which can be converted without loss of precision to an Option, the operation will fail with a run-time error.

## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

---
title: "AsToken Method"
ms.author: solsen
ms.custom: na
ms.date: 06/29/2017
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

# AsToken Method
Converts the value in a JsonObject to a JsonToken data type.

```
JsonToken := JsonObject.AsToken
```

### Parameters
*JsonObject*  
&emsp;Type: JsonObject

## Return Value
*JsonToken*  
&emsp;Type: JsonToken

The returned JsonToken contains the same data as the JsonObject, but allows for treating the data in a generic manner.

## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

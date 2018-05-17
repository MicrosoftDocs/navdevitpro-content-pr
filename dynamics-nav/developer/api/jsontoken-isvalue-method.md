---
title: "IsValue Property"
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
redirect_url: /dynamics365/business-central/dev-itpro/developer/devenv-restapi-overview
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# IsValue Property
Indicates whether a [JsonToken](jsontoken-class.md) represents a JSON value.

```
Ok := JsonToken.IsValue
```

### Parameters
*JsonToken*  
&emsp;Type: [JsonToken](jsontoken-class.md)

## Property Value/Return Value
&emsp;Type: [Boolean](../datatypes/devenv-boolean-data-type.md)

**True** if the JsonToken represents a JSON value; otherwise, **false**.

## See Also
[JsonToken](jsontoken-class.md)  
[JsonValue](jsonvalue-class.md)  
[HTTP, JSON, TextBuilder, and XML API](../devenv-restapi-overview.md)  
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

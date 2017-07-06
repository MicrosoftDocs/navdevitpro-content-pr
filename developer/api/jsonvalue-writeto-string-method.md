---
title: "WriteTo_String Method"
ms.author: SusanneWindfeldPedersen
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

# WriteTo_String Method

Serializes and writes the JSON data of the JsonValue to a given Text object.

```
[Ok := ] JsonValue.WriteTo(var Text)
```

## Parameters
*JsonValue*  
&emsp;Type: JsonValue

*String*  
&emsp;Type: Text

The Text object to which the JSON data will be written.

## Property Value/Return Value
Type: Boolean

**True** if the write was successful; otherwise, **false**.

If you omit this optional return value and if the write does not execute successfully, then a run-time error occurs.

## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

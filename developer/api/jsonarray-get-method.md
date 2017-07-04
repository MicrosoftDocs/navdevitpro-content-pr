---
title: "Get Method"
ms.author: SusanneWindfeldPedersen
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

# Get Method
Retrieves the value at the given index in the JsonArray.

```
[Ok := ] JsonArray.Get(Index, Result)
```

## Parameters
*Index*  
&emsp;Type: Integer

*Result*  
&emsp;Type: JsonToken

A variable of type JsonToken that will contain the result if the operation is successful.

## Return Value
Type: Boolean

**True** if the operation was successful; otherwise, **false**.

If you omit this optional return value and if the select does not execute successfully, then a run-time error occurs.

## Remarks
The operation will fail if the *Index* is smaller than 0 or greater or equal than JsonArray.Count.

## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions Using the New Development Environment](../devenv-dev-overview.md)

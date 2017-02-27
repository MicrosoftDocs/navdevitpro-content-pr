---
title: "AsTime Method"
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

# AsTime Method

Converts the value in a JsonValue to a **Time** data type.

```
Time := JsonValue.AsTime
```

## Parameters
*JsonValue*

Type: JsonValue

## Return Value
Type : Time

## Remarks
If the JsonValue does not contain a string of the format "HH:mm:ss.FFFFFFF" (https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx) the operation will fail with a run-time error. 

//TODO:Link to example about custom parsing.

## See Also


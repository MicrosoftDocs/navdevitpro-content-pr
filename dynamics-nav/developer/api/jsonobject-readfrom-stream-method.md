---
title: "ReadFrom_Stream Method"
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

# ReadFrom_Stream Method
Reads the JSON data from the stream into a JsonObject variable.

```
[Ok := ] JsonObject.ReadFrom(InStream)
```

## Parameters
*JsonObject*  
&emsp;Type: JsonObject

*InStream*  
&emsp;Type: InStream

The InStream object from which the JSON data will be read.

## Property Value/Return Value
Type: Boolean

**True** if the read was successful; otherwise, **false**.

If you omit this optional return value and if the read does not execute successfully, then a run-time error occurs.

## Remarks
1. This method can fail if the stream is in an invalid state or if the JSON data is malformed.
2. If the operation succeeds, the JsonObject will be disconnected from its current JSON tree and the data contained by the JsonObject will be replaced with the new value.
3. To delete the contents in a JsonObject variable use the Clear function.

```
Clear(JsonObject)
```

## Example
This example shows how to read JSON data from a stream into a JsonObject variable.

```
local procedure ReadJson(source : InStream) result : JsonObject;
begin
    result.ReadFrom(source);    
end;
```
## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

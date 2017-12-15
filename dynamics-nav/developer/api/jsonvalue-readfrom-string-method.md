---
title: "ReadFrom_String Method"
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

# ReadFrom_String Method

Reads the JSON data from the string into a JsonValue variable.

```
[Ok := ] JsonValue.ReadFrom(String)
```

## Parameters
*JsonValue*  
&emsp;Type: JsonValue

*String*  
&emsp;Type: [String](/datatypes/devenv-text-data-type.md)

The String object from which the JSON data will be read.

## Property Value/Return Value
&emsp;Type: [Boolean](/datatypes/devenv-boolean-data-type.md)

**True** if the read was successful; otherwise, **false**.

If you omit this optional return value and if the read does not execute successfully, then a run-time error occurs.

## Remarks
1. This method can fail if the JSON data is malformed..
2. If the operation succeeds, the JsonValue will be disconnected from its current JSON tree and the data contained by the JsonValue will be replaced with the new value.
3. To delete the contents in a JsonValue variable use the Clear function.

To delete the contents in a JsonValue variable use the **Clear** function.

```
Clear(JsonValue)
```

## Example
This example shows how to read JSON data from a string into a **JsonValue** variable.

```
local procedure ReadJson(data : Text) result : JsonValue;
begin
    result.ReadFrom(data);    
end;

```

## See Also
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

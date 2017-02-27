---
title: "ReadFrom_String Method"
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

# ReadFrom_String Method

Reads the JSON data from the string into a JsonToken variable.

```
[Ok := ] JsonToken.ReadFrom(String)
```

## Parameters
*JsonToken*
Type: JsonToken

*String*
Type: String

The String object from which we read the JSON data.

## Property Value/Return Value
Type : Boolean

**true** if the read was successful; otherwise, **false**. 
If you omit this optional return value and if the read does not execute successfully, then a run-time error occurs. 

## Remarks
This method can fail if JSON data is malformed.


To delete the contents in a JsonToken variable use the **Clear** function.

```
Clear(JsonToken)
```

## Example
This example shows how to read JSON data from a string into a **JsonToken** variable.

```
local procedure ReadJson(data : Text) result : JsonToken;
begin
    result.ReadFrom(data);    
end;

```

## See Also
---
title: "ReadFrom_Stream Method"
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
author: SusanneWindfeldPedersen
---

# ReadFrom_Stream Method

Reads the JSON data from the stream into a JsonToken variable.

```
[Ok := ] JsonToken.ReadFrom(InStream)
```

## Parameters
*JsonToken*
Type: JsonToken

*InStream*
Type: InStream

The InStream object from which we read the JSON data.

## Property Value/Return Value
Type : Boolean

**true** if the read was successful; otherwise, **false**.
If you omit this optional return value and if the read does not execute successfully, then a run-time error occurs.

## Remarks
1. This method can fail if the stream is in a non valid state or if the JSON data is malformed.
2. If the operation succeeds, the data contained by the JsonToken will be replaced with the new value.
3. To delete the contents in a JsonToken variable use the Clear function.

```
Clear(JsonToken)
```
## Example
This example shows how to read JSON data from a stream into a JsonToken variable.

```
local procedure ReadJson(source : InStream) result : JsonToken;
begin
    result.ReadFrom(source);    
end;

```
## See Also
[Getting Started](newdev-get-started.md)  
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)

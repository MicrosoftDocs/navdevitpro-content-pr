---
title: "JsonToken Class"
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

# JsonToken Class

A JsonToken object is a container for any well-formed JSON data. A default JsonToken object contains the JSON value of NULL.

The following methods are available on JsonToken objects.

|Method name|Description|
|-----------|-----------|
|[Path](jsontoken-path-method.md)|Retrieves the JSON path of the token relative to the root of its containing tree.|
|[ReadFrom_Stream](jsontoken-readfrom-stream-method.md)|Reads the JSON data from the stream into a JsonToken variable.|
|[ReadFrom_String](jsontoken-readfrom-string-method.md)|Reads the JSON data from the string into a JsonToken variable.|
|[WriteTo_Stream](jsontoken-writeto-stream-method.md)|Serializes and writes the JSON data of the JsonToken to a given OutStream object.|
|[WriteTo_String](jsontoken-writeto-string-method.md)|Serializes and writes the JSON data of the JsonToken to a given Text object.|
|[Clone](jsontoken-clone-method.md)|Creates a deep-copy of the JsonToken value.|
|[SelectToken](jsontoken-selecttoken-method.md)|Selects a JsonToken using a JPath expression.|
|[IsArray](jsontoken-isarray-method.md)|Indicates whether a JsonToken represents a JSON object.|
|[IsObject](jsontoken-isobject-method.md)|Indicates whether a JsonToken contains a JSON object.|
|[IsValue](jsontoken-isvalue-method.md)|Indicates whether a JsonToken contains a JSON object.|
|[AsArray](jsontoken-asarray-method.md)|Converts the value in a JsonToken to a JsonArray data type.|
|[AsObject](jsontoken-asobject-method.md)|Converts the value in a JsonToken to a JsonObject data type.|
|[AsValue](jsontoken-asvalue-method.md)|Converts the value in a JsonToken to a JsonValue data type.|

## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions Using the New Development Environment](../devenv-dev-overview.md)

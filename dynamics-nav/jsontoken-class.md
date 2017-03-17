---
title: "JsonToken Class"
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

# JsonToken Class

**JsonToken** object is a container for any well-formed JSON data. A default **JsonToken** contains the JSON value of NULL.

The following methods are available on the **JsonToken** class.

|Method name|Description|
|-----------|-----------|
|[AsArray](jsontoken-asarray-method.md)|Converts the value in a JsonToken to a **JsonArray** data type.|
|[AsObject](jsontoken-asobject-method.md)|Converts the value in a JsonToken to a **JsonObject** data type.|
|[AsValue](jsontoken-asvalue-method.md)|Converts the value in a JsonToken to a **JsonValue** data type.|
|[Clone](jsontoken-clone-method.md)|Creates a deep-copy of the JsonToken value.|
|[IsArray](jsontoken-isarray-method.md)|Indicates whether a JsonToken represents/contains a JSON object.|
|[IsObject](jsontoken-isobject-method.md)|Indicates whether a JsonToken represents/contains a JSON object.|
|[Path](jsontoken-path-method.md)|Retrieves the JSON path of the token relative to its containing tree.|
|[ReadFrom_Stream](jsontoken-readfrom-stream-method.md)|Reads the JSON data from the stream into a JsonToken variable.|
|[SelectToken](jsontoken-selecttoken-method.md)|Selects a **JsonToken** using a JPath expression.|
|[WriteTo_Stream](jsontoken-writeto-stream-method.md)|Serializes and writes the JSON data of the **JsonToken** to a given **Text** object.|
|[WriteTo_String](jsontoken-writeto-string-method.md)|Serializes and writes the JSON data of the JsonToken to a given Text object.|

## See Also
[Getting Started](newdev-get-started.md)  
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)

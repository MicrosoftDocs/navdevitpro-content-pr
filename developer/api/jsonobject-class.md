---
title: "JsonObject Class"
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

# JsonObject Class
A JsonObject object is a container for any well-formed JSON object. A default JsonObject contains an empty JSON object.

The following methods are available on JsonObject objects.

|Method name|Description|
|-----------|-----------|
|[Path](jsonobject-path-method.md)|Retrieves the JSON path of the object relative to the root of its containing tree.|
|[ReadFrom_Stream](jsonobject-readfrom-stream-method.md)|Reads the JSON data from the stream into a JsonObject variable.|
|[ReadFrom_String](jsonobject-readfrom-string-method.md)|Reads the JSON data from the string into a JsonObject variable.|
|[WriteTo_Stream](jsonobject-writeto-stream-method.md)|Serializes and writes the JSON data of the JsonObject to a given OutStream object.|
|[WriteTo_String](jsonobject-writeto-string-method.md)|Serializes and writes the JSON data of the JsonObject to a given Text object.|
|[Clone](jsontoken-clone-method.md)|Creates a deep-copy of the JsonObject value.|
|[SelectToken](jsontoken-selecttoken-method.md)|Selects a JsonToken using a JPath expression.|
|[AsToken](jsonobject-astoken-method.md)|Converts the value in the JsonObject to a JsonToken data type.|
|[Add](jsonobject-add-method.md)|Adds a new property to the JsonObject.|
|[Contains](jsonobject-contains-method.md)|Verifies if the JsonObject contains a property with a given key.|
|[Get](jsonobject-get-method.md)|Retrieves the value of a property with a given key from the JsonObject.|
|[Remove](jsonobject-remove-method.md)|Removes the property with the given key from the object.|
|[Replace](jsonobject-replace-method.md)|Replaces the value of the property with the given key with the new value.|
|[RemoveAll](jsonobject-removeall-method.md)|Removes all the properties of the given object.|

## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

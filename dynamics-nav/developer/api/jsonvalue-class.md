---
title: "JsonValue Class"
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

# JsonValue Class
JsonValue is a container for any well-formed fundamental JSON value. A default JsonValue is set to the JSON value of NULL.

The following methods are available on the JsonValue class.

|Method name|Description|
|-----------|-----------|
|[Path](jsonvalue-path-method.md)|Retrieves the JSON path of the value relative to the root of its containing tree.|
|[ReadFrom_Stream](jsonvalue-readfrom-stream-method.md)|Reads the JSON data from the stream into a JsonValue variable.|
|[ReadFrom_String](jsonvalue-readfrom-string-method.md)|Reads the JSON data from the string into a JsonValue variable.|
|[WriteTo_Stream](jsonvalue-writeto-stream-method.md)|Serializes and writes the JSON data of the JsonValue to a given OutStream object.|
|[WriteTo_String](jsonvalue-writeto-string-method.md)|Serializes and writes the JSON data of the JsonValue to a given Text object.|
|[Clone](jsontoken-clone-method.md)|Creates a deep-copy of the JsonValue value.|
|[AsToken](jsonvalue-astoken-method.md)|Converts the value in the JsonValue to a JsonToken data type.|
|[IsNull](jsonvalue-isnull-method.md)|Indicates whether the JsonValue contains the JSON value of NULL.|
|[IsUndefined](jsonvalue-isundefined-method.md)|Indicates whether the JsonValue contains the JSON value of UNDEFINED.|
|[AsBoolean](jsonvalue-asboolean-method.md)|Converts the value in a JsonValue to a Boolean data type.|
|[AsByte](jsonvalue-asbyte-method.md)|Converts the value in a JsonValue to a Byte data type.|
|[AsChar](jsonvalue-aschar-method.md)|Converts the value in a JsonValue to a Char data type.|
|[AsOption](jsonvalue-asoption-method.md)|Converts the value in a JsonValue to an Option data type.|
|[AsInteger](jsonvalue-asinteger-method.md)|Converts the value in a JsonValue to an Integer data type.|
|[AsBigInteger](jsonvalue-asbiginteger-method.md)|Converts the value in a JsonValue to an BigInteger data type.|
|[AsDecimal](jsonvalue-asdecimal-method.md)|Converts the value in a JsonValue to a Decimal data type.|
|[AsDuration](jsonvalue-asduration-method.md)|Converts the value in a JsonValue to a Duration data type.|
|[AsCode](jsonvalue-ascode-method.md)|Converts the value in a JsonValue to a Code data type.|
|[AsText](jsonvalue-astext-method.md)|Converts the value in a JsonValue to a Text data type.|
|[AsDate](jsonvalue-asdate-method.md)|Converts the value in a JsonValue to a Date data type.|
|[AsDateTime](jsonvalue-asdatetime-method.md)|Converts the value in a JsonValue to a DateTime data type.|
|[AsTime](jsonvalue-astime-method.md)|Converts the value in a JsonValue to a Time data type.|
|[SetValue](jsonvalue-setvalue-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given variable.|
|[SetValueToNull](jsonvalue-setvaluetonull-method.md)|Set the contents of the JsonValue variable to the JSON representation of NULL.|
|[SetValueToUndefined](jsonvalue-setvaluetoundefined-method.md)|Set the contents of the JsonValue variable to the JSON representation of UNDEFINED.|

## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

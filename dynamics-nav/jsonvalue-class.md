---
title: "JsonValue Class"
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

# JsonValue Class
JsonValue object is a container for any well-formed JSON object. A default JsonValue is set to the JSON value of NULL.

<!-- //TODO:
Copy and adapt from JsonToken:
Path,
ReadFrom_Stream,
ReadFrom_String,
SelectToken,
WriteTo_Stream,
WriteTo_String.

//TODO: Document serialization for Decimal, BigInteger, Date, DateTime, Time
//TODO: Add guidance for working with unsupported types

--> 

**JsonValue** object is a container for any well-formed JSON data. A default **JsonValue** contains the JSON value of NULL.

The following methods are available on the **JsonValue** class.

|Method name|Description|
|-----------|-----------|
|[AsBigInteger](jsonvalue-asbiginteger-method.md)|Converts the value in a JsonValue to an **BigInteger** data type.|
|[AsBoolean](jsonvalue-asboolean-method.md)|Converts the value in a JsonValue to a **Boolean** data type.|
|[AsByte](jsonvalue-asbyte-method.md)|Converts the value in a JsonValue to a **Byte** data type.|
|[AsChar](jsonvalue-aschar-method.md)|Converts the value in a JsonValue to a **Char** data type.|
|[AsCode](jsonvalue-ascode-method.md)|Converts the value in a JsonValue to a **Code** data type.|
|[AsDate](jsonvalue-asdate-method.md)|Converts the value in a JsonValue to a **Date** data type.|
|[AsDateTime](jsonvalue-asdatetime-method.md)|Converts the value in a JsonValue to a **DateTime** data type.|
|[AsDecimal](jsonvalue-asdecimal-method.md)|Converts the value in a JsonValue to a **Decimal** data type.|
|[AsDuration](jsonvalue-asduration-method.md)|Converts the value in a JsonValue to a **Duration** data type.|
|[AsInteger](jsonvalue-asinteger-method.md)|Converts the value in a JsonValue to a **Integer** data type.|
|[AsOption](jsonvalue-asoption-method.md)|Converts the value in a JsonValue to a **Option** data type.|
|[AsText](jsonvalue-astext-method.md)|Converts the value in a JsonValue to a **Text** data type.|
|[AsTime](jsonvalue-astime-method.md)|Converts the value in a JsonValue to a **Time** data type.|
|[AsToken](jsonvalue-astoken-method.md)|Converts the value in a JsonValue to a **JsonToken** data type.|
|[IsNull](jsonvalue-isnull-method.md)|Indicates whether the JsonValue contains the JSON value of NULL.|
|[IsUndefined](jsonvalue-isundefined-method.md)|Indicates whether the JsonValue contains the JSON value of UNDEFINED.|
|[SetValue](jsonvalue-setvalue-method.md)|Set the contents of the JsonValue variable to the JSON representation of the given variable.|
|[SetValueToNull](jsonvalue-setvaluetonull-method.md)|Set the contents of the JsonValue variable to the JSON representation of NULL.|
|[SetValueToUndefined](jsonvalue-setvaluetoundefined-method.md)|Set the contents of the JsonValue variable to the JSON representation of UNDEFINED.|

## See Also

## See Also

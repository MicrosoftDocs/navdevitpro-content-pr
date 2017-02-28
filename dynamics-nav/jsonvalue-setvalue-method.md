---
title: "SetValue Method"
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

# SetValue Method

Set the contents of the JsonValue variable to the JSON representation of the given variable.

```
JsonValue.SetValue(Value)
```

## Parameters
*Value*
Type: Boolean | Char | Byte | Option | Integer | BigInteger | Decimal | Duration | Date | Time | DateTime | String


### Remarks
1. When **Value** is a **Boolean** type, it will be stored and serialized as a **JSON Boolean** value.

2. When **Value** is a **Char**, **Byte**, **Option**, **Integer** type, integral value will be stored and serialized as a JSON Number.

3. When **Value** is **BigInteger**, **Decimal**, the value will be stored as a **String** to not lose precision. // TODO: Add reference to JSON-I recommendation

4. When **Value** is **Duration**, it's underlying value, representing a 64-bit integer (add reference to https://msdn.microsoft.com/en-us/library/dd355139.aspx) is stored and serialized as a BigInteger.

5. When **Value** is a **Date** type, it will be serialized in the format *yyyy-MM-dd*.

6. When **Value** is a **Time** type, it will be serialized as *HH:mm:ss.FFFFFFF* (https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)

7. When **Value** is a **DateTime** type, it will be serialized as *o* (*o* as specified https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx)

## See Also
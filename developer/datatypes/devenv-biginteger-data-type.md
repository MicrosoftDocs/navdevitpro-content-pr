---
title: "BigInteger Data Type"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 227f707b-04f6-47c6-9feb-0fb9499d11e5
caps.latest.revision: 9
manager: edupont
---
# BigInteger Data Type
Stores very large whole numbers that range from -9,223,372,036,854,775,807 to 9,223,372,036,854,775,807.  
  
## Remarks  
 This data type is a 64-bit integer.  
  
 You must add an L to the constant definition to inform AL that the integer must be interpreted and treated as a BigInteger.  
  
 If you assign -9,223,372,036,854,775,808 directly to a BigInteger variable, then you get an error when you try to compile the code. However, you can indirectly assign -9,223,372,036,854,775,808 to a BigInteger variable by using the following code.  
  
```  
BigIntegerVar := -9223372036854775807L;  
BigIntegerVar := BigIntegerVar - 1;  
```  
  
 If you try to indirectly assign a value that is smaller than -9,223,372,036,854,775,808, or larger than 9,223,372,036,854,775,807, then you get a run-time error.  
  
## Example  
  
```  
BI := 1L;  
BI := 455500000000L;  
```  
  
## See Also  
 [Decimal Data Type](devenv-decimal-data-type.md)   
 [Integer Data Type](devenv-integer-data-type.md)   
 [ABS method (Decimal, Integer, BigInteger)](devenv-abs-method-decimal-integer-biginteger.md)   
 [POWER method (Decimal, Integer, BigInteger)](devenv-power-method-decimal-integer-biginteger.md)   
 [RANDOM method (Integer)](devenv-random-method-integer.md)   
 [RANDOMIZE method (Integer)](devenv-randomize-method-integer.md)   
 [ROUND method (Decimal)](devenv-round-method-decimal.md)
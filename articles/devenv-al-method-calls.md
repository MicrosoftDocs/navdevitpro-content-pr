---
title: "AL Method Calls"
ms.custom: na
ms.date: 06/04/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-for-financials"
ms.assetid: 32f9ca49-8263-447f-986c-259c0e11a007
caps.latest.revision: 11
manager: edupont
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# AL Method Calls
AL contains several methods that can be used for different purposes, such as string handling, text formatting, database handling, and so on. Some of these methods can use different parameters.  
  
## Parameters  
 In a method call, the parameters are separated by commas, and the optional parameters may be omitted starting from the right. For example, this means that if a method has three optional parameters, then you cannot omit the second parameter without omitting the third parameter.  
  
 You can specify that a parameter is passed to a method by value or by reference.  
  
-   If a parameter is passed by value, then a copy of the variable is passed to the method. Any changes that the method makes to the value of the variable are local changes that affect only the copy, not the variable itself.  
  
-   If a parameter is passed by reference, then a reference to the variable is passed to the method. The method can change the value of the variable itself.  
  
 For more information about how to specify that a parameter is passed by value or by reference, see [How to: Add a Method to a Codeunit](How-to--Add-a-Method-to-a-Codeunit.md).  
  
### Example 1  
 The following shows the syntax for a method.  
  
```  
METHOD([Optional1] [, Optional2] [, Optional3])  
```  
  
 The method that uses the syntax above can be called by using the following code.  
  
```  
METHOD(Optional1, Optional2)  
```  
  
 This method cannot be called by using the following code.  
  
```  
FUNCTION(, Optional2, Optional3)  
```  
  
### Example 2  
 ABS is an example of an AL method that has a fixed number of parameters \(1\).  
  
```  
Value := -1033; //A negative integer value  
PositiveValue := ABS(Value); //Calculate the positive value 1033  
```  
  
### Example 3  
 The method DMY2DATE is an example of a method that can be called by using a variable number of parameters.  
  
```  
NewDate := DMY2DATE(5, 11, 1992); //Returns the date November 5, 1992  
```  
  
 Depending on the use of the DMY2DATE method, 1, 2, or 3 parameters can be passed to the method because the second and third parameters are optional. When the second and third parameters are not used, values from the system date are used as default.  
  
## Return Values  
 A method can return a value. For more information about how to specify that a method has a return value, see [How to: Add a Method to a Codeunit](How-to--Add-a-Method-to-a-Codeunit.md).  
  
### Example 1  
 You can assign the return value of a method to a variable.  
  
```  
ReturnVal := MyMethod(Param1);  
```  
  
### Example 2  
 In this example, MyMethod returns a Boolean value. You can use the return value in a conditional statement.  
  
```  
IF (MyMethod(Param1)) THEN  
  <Statement1>  
ELSE  
  <Statement2>  
```
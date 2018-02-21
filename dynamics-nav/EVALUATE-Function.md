---
title: "EVALUATE Function"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: dfd9bab5-eb17-4e12-b5de-3acafc336d60
caps.latest.revision: 10
---
# EVALUATE Function
Evaluates a string representation of a value into its typical representation. The result is assigned to a variable.  
  
## Syntax  
  
```  
  
[Ok :=] EVALUATE(Variable, String[, Number])  
```  
  
#### Parameters  
 *Variable*  
 Type: Any type of variable  
  
 The value of the string is assigned to the variable.  
  
 *String*  
 Type: Text constant or code  
  
 A string that contains a value of any simple C/AL data type.  
  
 *Number*  
 Type: Integer  
  
 This optional value can be used when exporting data with an XMLport. The only valid value is 9, which indicates that the data must be converted from XML format to C/SIDE format.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 Specifies whether an error occurred during the evaluation of the string.  
  
 If the return value is **true**, then no errors occurred during the evaluation of the string and the value was assigned to *Variable*.  
  
 If the return value is **false**, then errors occurred during the evaluation of the string and the original value of *Variable* was not modified.  
  
## Example  
 This example shows how to use the EVALUATE function when it is called with four different types of variables.  
  
 This example requires that you create the following variables and text constants in the **C/AL Globals** window.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|VarInteger|Integer|  
|VarDate|Date|  
|VarYesNo|Boolean|  
|VarDuration|Duration|  
|Value|Text|  
|Ok1|Boolean|  
|Ok1|Boolean|  
|Ok3|Boolean|  
|Ok4|Boolean|  
  
|Text constant|ENU value|  
|-------------------|---------------|  
|Text000|VarInteger = \#1\#\#\#\#\#\#. The return code is: %2.\\|  
|Text001|VarDate = \#3\#\#\#\#\#\#. The return code is: %4.\\|  
|Text002|VarYesNo = \#5\#\#\#\#\#\#. The return code is: %6.\\|  
|Text003|VarDuration = %7. The return code is: %8.|  
  
```  
Value := '010196';  
Ok1 := EVALUATE(VarInteger, Value);  
Ok2 := EVALUATE(VarDate, Value);  
Ok3 := EVALUATE(VarYesNo, Value);  
Value := '2days 4hours 3.7 seconds 17.3 milliseconds';  
Ok4 := EVALUATE(VarDuration, Value);  
MESSAGE(Text000 + Text001 + Text002 + Text003, VarInteger, Ok1, VarDate, Ok2, VarYesNo, Ok3, VarDuration, Ok4);  
```  
  
 The message window displays the following:  
  
 **VarInteger = 10196   . The return code is: Yes.**  
  
 **VarDate = 01/01/96. The return code is: Yes.**  
  
 **VarYesNo = No      . The return code is: No.**  
  
 **VarDuration = 2 days 4 hours 3 seconds 717 milliseconds. The return code is: Yes.**  
  
 This example shows that although Value \('010196'\) can be interpreted as both an integer and a date expression, it cannot be interpreted as a Boolean expression. This causes an error, shown in the return code Ok3 \(=FALSE\).  
  
 This example also shows that when you evaluate a string as a duration data type, you can use certain words in the string to describe the duration. The following words or abbreviations are supported:  
  
-   day, days, d  
  
-   hour, hours, h  
  
-   minute, minutes, min, m  
  
-   second, seconds, sec, s  
  
-   millisecond, milliseconds, milli, millis  
  
 You can include decimal values in the string that you evaluate as a duration. Decimal values for milliseconds are ignored; only the whole number is evaluated.  
  
## See Also  
 [CLEAR Function](CLEAR-Function.md)   
 [CLEARALL Function](CLEARALL-Function.md)   
 [COPYSTREAM Function](COPYSTREAM-Function.md)
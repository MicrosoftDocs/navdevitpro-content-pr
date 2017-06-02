---
title: "UPDATE Method (Dialog)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 7b41bb95-e7d9-4e7c-8ee8-5caf808caf5f
caps.latest.revision: 18
manager: edupont
---
# UPDATE Method (Dialog)
Updates the value of a '\#'-or '@' field in the active window.  
  
## Syntax  
  
```  
  
Dialog.UPDATE([Number] [, Value1])  
```  
  
#### Parameters  
 *Dialog*  
 Type: Dialog  
  
 The dialog box that you want to update.  
  
 *Number*  
 Type: Integer  
  
 Each '\#' or '@' field has a specific number. The Number argument tells into which field the Value should be inserted. If you omit this parameter, then all '\#' or '@' fields in the active window are updated.  
  
 *Value*  
 Type: Any  
  
 This value or expression can be any simple AL data type such as Boolean, Option, Integer, Decimal, Date, Time, Text, and Code. If you omit this value, then the value from the variable in the [OPEN Method \(Dialog\)](devenv-OPEN-Method-Dialog.md) call is used.  
  
## Remarks  
 This method is not supported by [!INCLUDE[nav_web](includes/nav_web_md.md)].  
  
 When you have a method that contains Dialog.UPDATE\(Number,Value\) and the value is a variant, you must format the text constant to make sure that the variant type can consume the text constant.  
  
 In [!INCLUDE[d365fin_md](../includes/d365fin_md.md)], the text constant is read as type AL\_TEXTCONST, which cannot be interpreted by the variant.  
  
 You can use the [FORMAT Method \(Code, Text\)](devenv-FORMAT-Method-Code--Text.md) to convert the text constant to a string type, which can be interpreted and displayed by the variant.  
  
## Example  
 The following example shows how to update '\#' fields in a window.  
  
 This code example requires that you create the following global variables and text constants.  
  
|Variable name|DataType|Length|  
|-------------------|--------------|------------|  
|AccountInfo|Text|1024|  
|AccountNo|Integer|Not applicable|  
|TotalSum|Decimal|Not applicable|  
|MyDialog|Dialog|Not applicable|  
  
|Text constant name|Constant value|  
|------------------------|--------------------|  
|Text000|Account no. \#1\#\#\#\#\#\#\\|  
|Text001|shows a total of $ \#2\#\#\#\#\#\#|  
  
```  
AccountInfo := Text000 + Text001;  
AccountNo := 5634;  
TotalSum := 1000;  
MyDialog.OPEN(AccountInfo); // Opens a window with '#'-fields.  
  
SLEEP(5000);  
MyDialog.UPDATE(1, AccountNo); // Fills in field 1.  
SLEEP(5000);  
MyDialog.UPDATE(2, TotalSum); // Fills in field 2.  
SLEEP(5000);  
```  
  
 When the dialog box first opens, the following information is displayed:  
  
 **Account no. . . . .        shows a total of $. . . . . . .**  
  
 After the first SLEEP call, the value of the *AccountNo* variable is inserted. After the second SLEEP call, the value of the *TotalSum* variable is inserted.  
  
## See Also  
 [Dialog Data Type](Dialog-Data-Type.md)   
 [OPEN Method \(Dialog\)](devenv-OPEN-Method-Dialog.md)
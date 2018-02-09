---
title: "BREAK Function (Report, XMLport)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 2a8a6ed5-d29b-4e77-b035-9b93afa653b6
caps.latest.revision: 15
author: jswymer
manager: edupont
---
# BREAK Function (Report, XMLport)
Exits from a loop or a trigger in a data item trigger of a report or XMLport.  

## Syntax  

```  
CurrReport.BREAK  
```  

```  
CurrXMLPort.BREAK  
```  

## Remarks  
 BREAK causes the current trigger to end. When used inside a loop, such as a WHILE-DO or REPEAT-UNTIL construction, BREAK interrupts the loop and causes the current trigger to end.  

 Compare this with the [QUIT Function \(Report, XMLport\)](QUIT-Function--Report--XMLport-.md).  

> [!TIP]  
>  You can also use the [C/AL BREAK Statement](C-AL-BREAK-Statement.md) to exit an iteration or loop. The difference is that the BREAK statement does not terminate the trigger. It just exits the loop.  

## Example  
 This example of code in a trigger on a report object requires that you create the following variable and text constant in the **C/AL Globals** window.  

|Variable name|DataType|  
|-------------------|--------------|  
|MyVar|Integer|  

|Text constant|ENU value|  
|-------------------|---------------|  
|Text000|The variable is now %1.|  

```  
MyVar := 0;  
REPEAT  
  MyVar := MyVar + 1;  
  IF MyVar = 5 THEN  
    CurrReport.BREAK;  
  MESSAGE(Text000,MyVar);  
UNTIL Myvar = 10;  
MESSAGE('After REPEAT-UNTIL loop'); //This statement is never called.  
```  

 When you run the previous code, the loop will end when MyVar is 5 and the execution of the current trigger ends. Statements after the loop are not executed.  

## See Also  
 [Report Data Type](Report-Data-Type.md)   
 [XMLport Data Type](XMLport-Data-Type.md)   
 [C/AL BREAK Statement](C-AL-BREAK-Statement.md)

---
title: "InStream.READTEXT Function"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 50e1d666-6a94-458e-bb76-298c73559c37
caps.latest.revision: 10
manager: edupont
---
# InStream.READTEXT Function
Reads text from an InStream object.  
  
## Syntax  
  
```  
  
[Read := ] InStream.ReadText(Text[, Length])  
```  
  
#### Parameters  
 *Text*  
 Type: Text  
  
 The variable that receives the characters that were read.  
  
 *Length*  
 Type: Integer  
  
 The number of characters to be read. If you do not specify this parameter, the maximum length of the string is used.  
  
## Property Value/Return Value  
 Type: Integer  
  
 The number of characters that were read.  
  
## Remarks  
 READTEXT reads the specified number of bytes, the maximum length of the string, or until the end of the line.  
  
 Data is read in text format.  
  
 If you do not use the optional return value and the data being read is less than the length requested to be read, an error message is displayed.  
  
 If you use the return value, you must verify the validity of the data that has been read.  
  
## Example  
 This example shows how to use the InStream.READTEXT function. This example requires that you create the following variables.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|FileTest|File|  
|StreamInTest|InStream|  
|Int|Integer|  
|Txt|Text|  
  
```  
FileTest.OPEN('c:\XMLDocs\NewTest.txt');  
FileTest.CREATEINSTREAM(StreamInTest);  
// Starting a loop  
WHILE NOT (StreamInTest.EOS) DO BEGIN  
  Int := StreamInTest.READTEXT(Txt,100);  
  MESSAGE(Txt + '\Size: ' + FORMAT(Int));  
END;  
FileTest.CLOSE();  
```  
  
## See Also  
 [InStream and OutStream Data Types](InStream-and-OutStream-Data-Types.md)   
 [InStream.READ Function](InStream.READ-Function.md)   
 [InStream.EOS Function](InStream.EOS-Function.md)
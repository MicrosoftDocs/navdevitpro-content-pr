---
title: "OutStream.WRITE Function"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: b8ad5f9c-7e9c-499d-b360-3180845a3b75
caps.latest.revision: 9
---
# OutStream.WRITE Function
Writes a specified number of bytes to the stream. Data is written in binary format.  
  
## Syntax  
  
```  
  
[Written := ] OutStream.Write(Variable[, Length])  
```  
  
#### Parameters  
 *Variable*  
 Type: Any  
  
 Contains the data to be written  
  
 *Length*  
 Type: Integer  
  
 The number of bytes to be written. In the case of data types other than string, code, and binary, if you specify a length that differs from the size of the variable, an error message is displayed.  
  
## Property Value/Return Value  
 Type: Integer  
  
 The number of bytes that were written.  
  
## Remarks  
 If the optional return value, *Written*, is not specified and it was not possible to write all the data, an error message is displayed.  
  
 If the return value is present, you must verify that all the data was streamed.  
  
## Example  
  
```  
recBinaries.FIND('-');  
recBinaries.Data.CREATEOUTSTREAM(OutStream);  
OutStream.WRITE('Secretary');  
OutStream.WRITE('Alice');  
OutStream.WRITE('Hart');  
OutStream.WRITE(010696D);  
recBinaries.MODIFY();  
```  
  
## See Also  
 [InStream and OutStream Data Types](InStream-and-OutStream-Data-Types.md)   
 [OutStream.WRITETEXT Function](OutStream-WRITETEXT-Function.md)
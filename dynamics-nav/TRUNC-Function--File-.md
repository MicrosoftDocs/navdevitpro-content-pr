---
title: "TRUNC Function (File)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 1b634423-307e-424e-bce5-c7fe5c87331a
caps.latest.revision: 9
---
# TRUNC Function (File)
Truncate an ASCII or binary file to the current position of the file pointer.  
  
## Syntax  
  
```  
  
File.TRUNC  
```  
  
#### Parameters  
 *File*  
 Type: File  
  
 Use this variable to refer to the file.  
  
## Remarks  
 Typically, you use this function together with [SEEK Function \(File\)](SEEK-Function--File-.md). Use File.SEEK to position the pointer in the file and then use File.TRUNC to truncate the file at that point.  
  
## Example  
 The following example sets a pointer at position 20 in a file and truncates the file at the pointer position. The [WRITEMODE Function \(File\)](WRITEMODE-Function--File-.md) allows the file that is named C:\\TestFolder\\TestFile.txt to open in write mode. The SEEK function sets a pointer at position 20 in the file and then the [TRUNC Function \(FILE\)](TRUNC-Function--File-.md) truncates the contents at the pointer position. This example assumes that you have created a text file named C:\\TestFolder\\TestFile.txt. The file is then saved a truncated file. This example requires that you create the following variable in the **C/AL Globals** window.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|TestFile|File|  
  
```  
  
TestFile.WRITEMODE(TRUE);  
TestFile.OPEN('C:\TestFolder\TestFile.txt');  
TestFile.SEEK(20);  
TestFile.TRUNC;  
  
```  
  
## See Also  
 [File Data Type](File-Data-Type.md)
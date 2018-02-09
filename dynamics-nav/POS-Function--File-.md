---
title: "POS Function (File)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: eddb80ee-90a1-4657-a55f-b531bc363270
caps.latest.revision: 7
---
# POS Function (File)
Gets the current position of the file pointer in an ASCII or binary file.  
  
## Syntax  
  
```  
  
Position := File.POS  
```  
  
#### Parameters  
 *File*  
 Type: file  
  
 Use this variable to refer to the file.  
  
## Property Value/Return Value  
 Type: Integer  
  
 This show the current position of the file pointer in bytes.  
  
## Remarks  
 This function is often used with [LEN Function \(File\)](LEN-Function--File-.md) and [SEEK Function \(File\)](SEEK-Function--File-.md).  
  
## Example  
 The following example opens a text file that is named C:\\TestFolder\\TestFile.txt. The [WRITEMODE Function \(File\)](WRITEMODE-Function--File-.md) enables the file to be open in write mode. The POS function retrieves the position of the file pointer and stores it in the Position variable. When the file is open, the position of the pointer is 0 because a pointer is not set. The [SEEK Function \(File\)](SEEK-Function--File-.md) function sets a file pointer at position 5. After the [SEEK Function \(File\)](SEEK-Function--File-.md) is executed, the POS function returns 5 as the file pointer position. This example assumes that you have created a text file named C:\\TestFolder\\TestFile.txt. This example requires that you create the following variables in the **C/AL Globals** window.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|TestFile|File|  
|Position|Integer|  
  
```  
  
TestFile.WRITEMODE(TRUE);  
TestFile.OPEN('C:\TestFolder\TestFile.txt');  
Position := TestFile.POS;  
MESSAGE('Pointer position before SEEK: %1', Position);  
Testfile.SEEK(5);  
Position := Testfile.POS;  
MESSAGE('Pointer position after SEEK: %1', Position);  
```  
  
## See Also  
 [File Data Type](File-Data-Type.md)
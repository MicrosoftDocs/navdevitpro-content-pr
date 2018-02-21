---
title: "CREATE Function (File)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: b37c1137-eab2-42f9-aedd-e3559b3b678d
caps.latest.revision: 20
---
# CREATE Function (File)
Creates and opens an ASCII or binary file. If the file already exists, it will be truncated and then opened.  
  
## Syntax  
  
```  
  
[Ok := ] File.CREATE(Name[,TextEncoding.value])  
```  
  
#### Parameters  
 *File*  
 Type: File  
  
 Specifies the file to create.  
  
 *Name*  
 Type: Text or code  
  
 The name of the file that include the path. The following rules apply:  
  
-   You can omit the drive designation if the file is located on the current drive.  
  
-   You can omit the full path if the file is located in the current directory.  
  
-   You can enter only the subdirectory name if the file is located in a subdirectory of the current directory.  
  
 *TextEncoding*  
 Value: **MsDos**, **UTF8**, **UTF16**, or **Windows**  
  
 Optionally, you can specify the encoding on the file. By specifying the text encoding, you ensure that all the language-specific characters are represented correctly in [!INCLUDE[navnow](includes/navnow_md.md)] when you read data and write data.  
  
 For more information, see [Text Encoding](Text-Encoding.md).  
  
## Property Value/Return Value  
 Type: Boolean  
  
 Specifies whether the file was created.  
  
 **true** if the file was created; otherwise, **false**.  
  
## Remarks  
 If the [TEXTMODE Function \(File\)](TEXTMODE-Function--File-.md) returns **true** and you read or write to the file, text is put in the buffer.  
  
 If the [TEXTMODE Function \(File\)](TEXTMODE-Function--File-.md) function returns **false**, binary information is put in the buffer.  
  
 If you call CREATE on a File variable that refers to an open file, the function does not automatically close the existing file and create the new file. You must explicitly call the [CLOSE Function \(File\)](CLOSE-Function--File-.md) to close the existing file. Otherwise, a run-time error occurs.  
  
## Example  
 The following example creates a file that is named TestFile.txt in the path C:\\TestFolder\\. The TestFile variable stores the file and path that is created. If the file is created, a message that states that the file is created is displayed. Otherwise, an error message is displayed. This example requires that you create the following variable in the **C/AL Globals** window.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|TestFile|File|  
  
```  
  
IF TestFile.CREATE('C:\TestFolder\TestFile.txt') THEN BEGIN  
  MESSAGE('%1 is created', TestFile.NAME)  
END  
ELSE  
ERROR('The file could not be created');  
```  
  
## See Also  
 [File Data Type](File-Data-Type.md)   
 [Text Encoding](Text-Encoding.md)
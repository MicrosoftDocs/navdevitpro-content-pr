---
title: "EXPORT Function (BLOB)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 85dedf11-5fc2-4677-b683-e6a63b035ff9
caps.latest.revision: 11
manager: edupont
---
# EXPORT Function (BLOB)
Exports a binary large object \(BLOB\).  
  
## Syntax  
  
```  
  
[ExportName] := Blob.EXPORT([Name [, CommonDialog]])  
```  
  
#### Parameters  
 *Blob*  
 Type: Variable  
  
 The BLOB that you want to export.  
  
 *Name*  
 Type: Text or code  
  
 The path and name of the BLOB that you want to export.  
  
 When you enter the path, consider these shortcuts:  
  
-   You can omit the drive letter if the command is located on the current drive.  
  
-   You can omit the full path if the command is located in the current directory.  
  
-   You can enter only the subdirectory name if the command is located in a subdirectory of the current directory.  
  
 *CommonDialog*  
 Type: Boolean  
  
 Specifies whether you want to display a dialog box before the BLOB is exported. This dialog box lets you select the file that you want to export. Based on the [SubType Property \(BLOB\)](SubType-Property--BLOB-.md) property, only the appropriate file types are listed, such as bitmap files \(\*.bmp\), memo files \(\*.txt\), or all files \(\*.\*\).  
  
 If the *CommonDialog* parameter is **true**, [!INCLUDE[navnow](includes/navnow_md.md)] will display the confirmation dialog box. If the *CommonDialog* parameter is **false** \(default\), [!INCLUDE[navnow](includes/navnow_md.md)] will not display the confirmation dialog box.  
  
## Property Value/Return Value  
 Type: text  
  
 The name and path of the exported file.  
  
 If the return value is the file's name and path, then the BLOB was exported.  
  
 If the return value is an empty string, then the BLOB was not exported.  
  
## See Also  
 [BLOB Data Type](BLOB-Data-Type.md)
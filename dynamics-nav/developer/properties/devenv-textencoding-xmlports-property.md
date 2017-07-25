---
title: "TextEncoding Property (XMLports)"
ms.custom: na
ms.date: 06/14/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: cecfed61-dfea-4eb7-be2c-5b5091f765c5
caps.latest.revision: 25
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# TextEncoding Property (XMLports)
Specifies the [File Handling and Text Encoding](../devenv-file-handling-and-text-encoding.md) format to use when you use an XMLport to export or import data as text.  
  
## Applies to  
 XMLports  
  
> [!NOTE]  
>  The **TextEncoding** property is only available when the [Format Property \(XMLports\)](devenv-format-xmlports-property.md) of the XMLport is set to **Fixed Text** or **Variable Text**.  
  
## Values  
  
-   MS-DOS \(default\)  
  
-   UTF-8  
  
-   UTF-16  
  
-   Windows  
  
 For more information, see [[File Handling and Text Encoding](../devenv-file-handling-and-text-encoding.md).  
  
## Remarks  
 [File Handling and Text Encoding](../devenv-file-handling-and-text-encoding.md) is the process of transforming bytes of data into readable characters for users of a system or program. There are several industry [File Handling and Text Encoding](../devenv-file-handling-and-text-encoding.md) formats and different systems support different formats. Internally, [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] uses Unicode encoding. For exporting and importing data with an XMLport, [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] supports MS-DOS, UTF-8, UTF-16, and Windows encoding formats.  
  
 You should set the **TextEncoding** property to the encoding format that is compatible with the system or program that you will be exporting to or importing from. The following sections describe the available [File Handling and Text Encoding](../devenv-file-handling-and-text-encoding.md) formats.  
  
> [!TIP]  
>  You can also set the **TextEncoding** property in AL code. For example, if your XMLport can import or export different formats based on certain conditions, you can change the encoding on the fly depending on the conditions. For example, you can write code such as the following:  
>   
>  `currXMLport.TEXTENCODING := TEXTENCODING::Windows;`  
  
## Example  
 The following code example illustrates how you can set the encoding during run time.  
  
```  
...  
      CASE MyDefinitionTable."File Encoding" OF  
        MyDefinitionTable."File Encoding"::"MS-DOS":  
          currXMLport.TEXTENCODING(TEXTENCODING::MSDos);  
        MyDefinitionTable."File Encoding"::"UTF-8":  
          currXMLport.TEXTENCODING(TEXTENCODING::UTF8);  
        MyDefinitionTable."File Encoding"::"UTF-16":  
          currXMLport.TEXTENCODING(TEXTENCODING::UTF16);  
        MyDefinitionTable."File Encoding"::WINDOWS:  
          currXMLport.TEXTENCODING(TEXTENCODING::Windows);  
...  
```  
  
 The code example is based on XMLport 1220 in the [!INCLUDE[demolong](../includes/demolong_md.md)]. The table, **MyDefinitionTable**, has a field, **File Encoding**, that specifies the encoding for this part of an import.  
  
## See Also  
 [XMLports Properties](devenv-XMLport-properties.md)   
 [Format Property \(XMLports\)](devenv-format-xmlports-property.md)   
 [[File Handling and Text Encoding](../devenv-file-handling-and-text-encoding.md)
 <!-- [Text Encoding](../devenv-Text-Encoding.md) 
 [How to: Create XMLports](How-to--Create-XMLports.md)  
 [Walkthrough: Importing Data from Text Files to Tables](Walkthrough--Importing-Data-from-Text-Files-to-Tables.md) -->
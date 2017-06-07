---
title: "BLOB Data Type"
author: edupont04
manager: edupont04
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 09f7efd9-541f-4eae-b6e3-70576bfa0ca1
caps.latest.revision: 15
---
# BLOB Data Type
A binary large object (BLOB) is a complex data type. Variables of this data type differ from normal numeric and string variables in that BLOBs have a variable length.  

 The maximum size of a BLOB is 2 GB.  

## Remarks  
 Use BLOBs to store memos (text), pictures (bitmaps), or user-defined types.  

> [!NOTE]  
>  You cannot view text that is stored in BLOBs from the development environment.  

 You can read from and write to BLOBs by creating input and output streams, respectively. To do so, use [CREATEINSTREAM method (BLOB)](../methods/devenv-createinstream-method-blob.md) and [CREATEOUTSTREAM method (BLOB)](../methods/devenv-createoutstream-method-blob.md).  

 For more information, see [InStream and OutStream Data Types](InStream-and-OutStream-Data-Types.md).  

 To optimize performance, when you access a record that has a BLOB field, the data in the BLOB is not always read into memory. You must call the [CALCFIELDS method \(Record\)](../methods/devenv-CALCFIELDS-method-Record.md) to read the BLOB into memory and calculate it. Then you can use the BLOB in AL code or display it in the application.  

 It is not supported to insert a BLOB field into a Variant.  

 It is not supported for a page to access a BLOB field from a table other than the SourceTable of the page.  

## See Also  
[CREATEINSTREAM method (BLOB)](../methods/CREATEINSTREAM-method-BLOB.md)  
[CREATEOUTSTREAM method (BLOB)](../methods/CREATEOUTSTREAM-method-BLOB.md)  
[EXPORT method (BLOB)](../methods/EXPORT-method-BLOB.md)  
[HASVALUE method (BLOB)](../methods/HASVALUE-method-BLOB.md)   
[Variant Data Type](Variant-data-type.md)

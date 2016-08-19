---
title: "BLOB Data Type"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 09f7efd9-541f-4eae-b6e3-70576bfa0ca1
caps.latest.revision: 15
manager: edupont
---
# BLOB Data Type
A binary large object \(BLOB\) is a complex data type. Variables of this data type differ from normal numeric and string variables in that BLOBs have a variable length.  
  
 The maximum size of a BLOB is 2 GB.  
  
## Remarks  
 Use BLOBs to store memos \(text\), pictures \(bitmaps\), or user\-defined types.  
  
> [!NOTE]  
>  You cannot view text that is stored in BLOBs from the development environment.  
  
 You can read from and write to BLOBs by creating input and output streams, respectively. To do so, use [CREATEINSTREAM Function \(BLOB\)](CREATEINSTREAM-Function--BLOB-.md) and [CREATEOUTSTREAM Function \(BLOB\)](CREATEOUTSTREAM-Function--BLOB-.md).  
  
 For more information, see [InStream and OutStream Data Types](InStream-and-OutStream-Data-Types.md).  
  
 To optimize performance, when you access a record that has a BLOB field, the data in the BLOB is not always read into memory. You must call the [CALCFIELDS Function \(Record\)](CALCFIELDS-Function--Record-.md) to read the BLOB into memory and calculate it. Then you can use the BLOB in C\/AL code or display it in the application.  
  
 It is not supported to insert a BLOB field into a Variant.  
  
 It is not supported for a page to access a BLOB field from a table other than the SourceTable of the page.  
  
## Differences Between [!INCLUDE[navnowlong](includes/navnowlong_md.md)] and Previous Versions  
 In previous versions of [!INCLUDE[navnow](includes/navnow_md.md)], if you wrote to a BLOB OutStream but did not insert or modify the record in the database, and then called the CALCFIELDS function on the BLOB field, you would get the value of the BLOB based on what you wrote to the OutStream, not based on what was currently in the database. In [!INCLUDE[navnowlong](includes/navnowlong_md.md)] in the same scenario, you get the value of the BLOB that is in the database. Similarly, in [!INCLUDE[navnowlong](includes/navnowlong_md.md)] if you call the CALCFIELDS Function on a new record that has not been inserted into the database, then you clear the BLOB field from the record.  
  
## See Also  
 [CREATEINSTREAM Function \(BLOB\)](CREATEINSTREAM-Function--BLOB-.md)   
 [CREATEOUTSTREAM Function \(BLOB\)](CREATEOUTSTREAM-Function--BLOB-.md)   
 [HASVALUE Function \(BLOB\)](HASVALUE-Function--BLOB-.md)   
 [Variant Data Type](Variant-Data-Type.md)
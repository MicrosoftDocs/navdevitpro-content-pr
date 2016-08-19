---
title: "InStream and OutStream Data Types"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d16b1998-7b14-4aca-9848-3882ca5a92f0
caps.latest.revision: 9
---
# InStream and OutStream Data Types
Reads from or writes to files and BLOBs.  
  
## Remarks  
 The InStream \(input stream\) and OutStream \(output stream\) data types are generic stream objects that you can use to read from or write to files and BLOBs. In addition, the InStream and OutStream data types enable data to be read from and sent to [Automation Data Type](../dynamics-nav/Automation-Data-Type.md) objects and [OCX Data Type](../dynamics-nav/OCX-Data-Type.md) objects. The Microsoft XML DOM can read from an InStream object and write to an OutStream object.  
  
 You can define the internal structure of a stream as a flat stream of bytes. You can assign one stream to another. Reading from and writing to a stream occurs sequentially.  
  
 You can create a stream object by using the following functions:  
  
-   [CREATEINSTREAM Function \(BLOB\)](../dynamics-nav/CREATEINSTREAM-Function--BLOB-.md)  
  
-   [CREATEOUTSTREAM Function \(BLOB\)](../dynamics-nav/CREATEOUTSTREAM-Function--BLOB-.md)  
  
-   [CREATEINSTREAM Function \(File\)](../dynamics-nav/CREATEINSTREAM-Function--File-.md)  
  
-   [CREATEOUTSTREAM Function \(File\)](../dynamics-nav/CREATEOUTSTREAM-Function--File-.md)  
  
 You can use InStream in the following ways:  
  
-   [COPYSTREAM Function](../dynamics-nav/COPYSTREAM-Function.md)  
  
-   [InStream.READ Function](../dynamics-nav/InStream.READ-Function.md)  
  
-   [InStream.EOS Function](../dynamics-nav/InStream.EOS-Function.md)  
  
-   [InStream.READTEXT Function](../dynamics-nav/InStream.READTEXT-Function.md)  
  
 You can use OutStream in the following ways:  
  
-   [COPYSTREAM Function](../dynamics-nav/COPYSTREAM-Function.md)  
  
-   [OutStream.WRITE Function](../dynamics-nav/OutStream.WRITE-Function.md)  
  
-   [OutStream.WRITETEXT Function](../dynamics-nav/OutStream.WRITETEXT-Function.md)
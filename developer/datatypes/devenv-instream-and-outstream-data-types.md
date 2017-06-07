---
title: "InStream and OutStream Data Types"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: d16b1998-7b14-4aca-9848-3882ca5a92f0
caps.latest.revision: 9
---
# InStream and OutStream Data Types
Reads from or writes to files and BLOBs.  
  
## Remarks  
 The InStream \(input stream\) and OutStream \(output stream\) data types are generic stream objects that you can use to read from or write to files and BLOBs. In addition, the InStream and OutStream data types enable data to be read from and sent to [Automation Data Type](Automation-Data-Type.md) objects and [OCX Data Type](OCX-Data-Type.md) objects. The Microsoft XML DOM can read from an InStream object and write to an OutStream object.  
  
 You can define the internal structure of a stream as a flat stream of bytes. You can assign one stream to another. Reading from and writing to a stream occurs sequentially.  
  
 You can create a stream object by using the following methods:  
  
-   [CREATEINSTREAM method \(BLOB\)](../methods/devenv-CREATEINSTREAM-method-BLOB.md)  
  
-   [CREATEOUTSTREAM method \(BLOB\)](../methods/devenv-CREATEOUTSTREAM-method-BLOB.md)  
  
-   [CREATEINSTREAM method \(File\)](../methods/devenv-CREATEINSTREAM-method-File.md)  
  
-   [CREATEOUTSTREAM method \(File\)](../methods/devenv-CREATEOUTSTREAM-method-File.md)  
  
 You can use InStream in the following ways:  
  
-   [COPYSTREAM method](../methods/devenv-COPYSTREAM-method.md)  
  
-   [InStream.READ method](../methods/devenv-InStream.READ-method.md)  
  
-   [InStream.EOS method](../methods/devenv-InStream.EOS-method.md)  
  
-   [InStream.READTEXT method](../methods/devenv-InStream.READTEXT-method.md)  
  
 You can use OutStream in the following ways:  
  
-   [COPYSTREAM method](../methods/devenv-COPYSTREAM-method.md)  
  
-   [OutStream.WRITE method](../methods/devenv-OutStream-WRITE-method.md)  
  
-   [OutStream.WRITETEXT method](../methods/devenv-OutStream-WRITETEXT-method.md)
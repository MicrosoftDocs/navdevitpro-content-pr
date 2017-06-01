---
title: "CurrentPath Property"
ms.custom: na
ms.date: 06/01/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: ff3dbf35-e1de-48f4-967f-1c8c3ae05e26
caps.latest.revision: 2
manager: edupont
---
# CurrentPath Property
Returns the path of the current node as a text string.  
  
## Applies To  
  
-   XMLports  
  
## Remarks  
 You set the **CurrentPath** property in AL code on a function or trigger. For example, you can write code such as the following:  
  
 `currXMLport.CURRENTPATH`  
  
 Each node in the path is separated by a ‘`/`’, for example, `/Root/Vendors/Vendor/Name`.  
  
 For an example of how to use this property, see XMLPort 1232, **Exp. Bank Data Conv. Serv.-CT**, in the [!INCLUDE[demolong](includes/demolong_md.md)] and refer to the `LOCAL GetValue(PostExchNo : Integer;LineNo : Integer) : Text` function.  
  
## See Also  
 [Properties](Properties.md)
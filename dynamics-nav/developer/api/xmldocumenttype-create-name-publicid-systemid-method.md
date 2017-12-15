---
title: "Create Method"
ms.author: solsen
ms.custom: na
ms.date: 07/20/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 620f0e32-eadc-43e9-8f6e-8fc0b12c3aaf
caps.latest.revision: 1
manager: edupont
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# Create Method
Creates an XmlDocumentType node.  
```  
XmlDocumentType := XmlDocumentType.Create(Name, PublicId, SystemId)  
```  
## Parameters
*Name*    
&emsp;Type: [String](/datatypes/devenv-text-data-type.md)  
A string that contains the qualified name of the DTD, which is the same as the qualified name of the root element of the XML document.  
  
*PublicId*    
&emsp;Type: [String](/datatypes/devenv-text-data-type.md)  
A string that contains the public identifier of an external public DTD.  
  
*SystemId*    
&emsp;Type: [String](/datatypes/devenv-text-data-type.md)  
A string that contains the system identifier of an external private DTD.  
  
## Return Value
*XmlDocumentType*  
&emsp;Type: XmlDocumentType  
  
## See Also
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

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
Creates an XmlElement node.  
```  
XmlElement := XmlElement.Create(LocalName, NamespaceUri, Content,...)  
```  
## Parameters
*LocalName*    
&emsp;Type: String  
The local name of the element to create.  
  
*NamespaceUri*    
&emsp;Type: String  
The namespace URI of the element to create.  
  
*Content*    
&emsp;Type: Joker  
The content to add to the element to create.  
  
## Return Value
*XmlElement*  
&emsp;Type: XmlElement  
  
## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

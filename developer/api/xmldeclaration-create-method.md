---
title: "Create Method"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 30/06/2017
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
Creates an XmlDeclaration node.  
```  
XmlDeclaration := XmlDeclaration.Create(Version, Encoding, Standalone)  
```  
## Parameters
*Version*    
&emsp;Type: String  
The version of the XML, usually "1.0".  
  
*Encoding*    
&emsp;Type: String  
The encoding for the XML document.  
  
*Standalone*    
&emsp;Type: String  
A string containing "yes" or "no" that specifies whether the XML is standalone or requires external entities to be resolved.  
  
## Return Value
*XmlDeclaration*  
&emsp;Type: XmlDeclaration  
  
## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

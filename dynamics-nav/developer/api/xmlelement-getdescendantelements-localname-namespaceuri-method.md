---
title: "GetDescendantElements Method"
ms.author: solsen
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

# GetDescendantElements Method
Gets a list containing the descendant elements for this element, in document order.  
```  
DescendantElements := XmlElement.GetDescendantElements(LocalName, NamespaceUri)  
```  
## Parameters
*LocalName*    
&emsp;Type: String  
The local name of the elements to retrieve.  
  
*NamespaceUri*    
&emsp;Type: String  
The namespace URI of the elements to retrieve.  
  
## Return Value
*DescendantElements*  
&emsp;Type: XmlNodeList  
  
## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

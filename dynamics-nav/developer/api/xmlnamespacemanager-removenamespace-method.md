---
title: "RemoveNamespace Method"
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

# RemoveNamespace Method
Removes the given namespace for the given prefix.  
```  
XmlNamespaceManager.RemoveNamespace(Prefix, Uri)  
```  
## Parameters
*Prefix*    
&emsp;Type: [String](/datatypes/devenv-text-data-type.md)  
The prefix for the namespace  
  
*Uri*    
&emsp;Type: [String](/datatypes/devenv-text-data-type.md)  
The namespace to remove for the given prefix. The namespace removed is from the current namespace scope. Namespaces outside the current scope are ignored.  
  
## See Also
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

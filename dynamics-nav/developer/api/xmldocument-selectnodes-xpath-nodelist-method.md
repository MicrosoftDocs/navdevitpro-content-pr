---
title: "SelectNodes Method"
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

# SelectNodes Method
Selects a list of nodes matching the XPath expression.  
```  
[Ok := ] XmlDocument.SelectNodes(XPath, NodeList)  
```  
## Parameters
*XPath*    
&emsp;Type: [String](/datatypes/devenv-text-data-type.md)  
The XPath expression.  
  
*NodeList*    
&emsp;Type: XmlNodeList  
An XmlNodeList containing a collection of nodes matching the XPath expression.  
  
## Return Value
*Ok*  
&emsp;Type: [Boolean](/datatypes/devenv-boolean-data-type.md)  
**true** if the operation was successful; otherwise, **false**.  
If you omit this optional return value and the operation does not execute successfully, a run-time error will occur.  
  
## See Also
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

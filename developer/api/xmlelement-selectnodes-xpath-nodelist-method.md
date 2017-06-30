---
title: "SelectNodes Method"
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

# SelectNodes Method
Selects a list of nodes matching the XPath expression.  
```  
[Ok := ] XmlElement.SelectNodes(XPath, NodeList)  
```  
## Parameters
*XPath*    
&emsp;Type: String  
The XPath expression.  
  
*NodeList*    
&emsp;Type: XmlNodeList  
An XmlNodeList containing a collection of nodes matching the XPath expression.  
  
## Return Value
*Ok*  
&emsp;Type: Boolean  
**true** if the operation was successful; otherwise, **false**.  
If you omit this optional return value and the operation does not execute successfully, a run-time error will occur.  
  
## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions Using the New Development Environment](../devenv-dev-overview.md)  

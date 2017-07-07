---
title: "SelectSingleNode Method"
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

# SelectSingleNode Method
Selects the first XmlNode that matches the XPath expression.  
```  
[Ok := ] XmlText.SelectSingleNode(XPath, Node)  
```  
## Parameters
*XPath*    
&emsp;Type: String  
The XPath expression.  
  
*Node*    
&emsp;Type: XmlNode  
The first XmlNode that matches the XPath query.  
  
## Return Value
*Ok*  
&emsp;Type: Boolean  
**true** if the operation was successful; otherwise, **false**.  
If you omit this optional return value and the operation does not execute successfully, a run-time error will occur.  
  
## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

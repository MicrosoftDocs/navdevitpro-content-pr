---
title: "Add Method"
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

# Add Method
Adds the specified content as a child of this element.  
```  
[Ok := ] XmlElement.Add(Content,...)  
```  
## Parameters
*Content*    
&emsp;Type: Joker  
The content to be added as a child of this element.  
  
## Return Value
*Ok*  
&emsp;Type: [Boolean](/datatypes/devenv-boolean-data-type.md)  
**true** if the operation was successful; otherwise, **false**.  
If you omit this optional return value and the operation does not execute successfully, a run-time error will occur.  
  
## See Also
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

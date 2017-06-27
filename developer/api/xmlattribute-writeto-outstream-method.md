---
title: "WriteTo Method"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 27/06/2017
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

# WriteTo Method
Serializes and saves the current node to the given variable.  
```  
[Ok := ] XmlAttribute.WriteTo(OutStream)  
```  
## Parameters
*OutStream*    
&emsp;Type: OutStream  
The OutStream to which you want to save.  
  
## Return Value
*Ok*  
&emsp;Type: Boolean  
**true** if the operation was successful; otherwise, **false**.  
If you omit this optional return value and the operation does not execute successfully, a run-time error will occur.  
  
## See Also
[Getting Started](devenv-get-started.md)  
[Developing Extensions Using the New Development Environment](devenv-dev-overview.md)  

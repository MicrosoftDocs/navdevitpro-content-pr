---
title: "Remove Method"
ms.author: SusanneWindfeldPedersen
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

# Remove Method
Removes the specified range of characters from this instance.  
```  
[Ok := ] TextBuilder.Remove(StartIndex, Count)  
```  
## Parameters
*StartIndex*    
&emsp;Type: Integer  
The one-based position in this instance where removal begins.  
  
*Count*    
&emsp;Type: Integer  
The number of characters to remove.  
  
## Return Value
*Ok*  
&emsp;Type: Boolean  
**True** if the operation was successful; otherwise, **false**.  
If you omit this optional return value and the operation does not execute successfully, a run-time error will occur.  
  
## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions Using the New Development Environment](../devenv-dev-overview.md)  

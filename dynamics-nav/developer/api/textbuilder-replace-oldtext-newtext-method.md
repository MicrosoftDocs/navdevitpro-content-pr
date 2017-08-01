---
title: "Replace Method"
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

# Replace Method
Replaces all occurrences of a specified string in this instance with another specified string.  
```  
[Ok := ] TextBuilder.Replace(OldText, NewText)  
```  
## Parameters
*OldText*    
&emsp;Type: Text  
The string to replace.  
  
*NewText*    
&emsp;Type: Text  
The string that replaces OldText.  
  
## Return Value
*Ok*  
&emsp;Type: Boolean  
**True** if the operation was successful; otherwise, **false**.  
If you omit this optional return value and the operation does not execute successfully, a run-time error will occur.  
  
## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

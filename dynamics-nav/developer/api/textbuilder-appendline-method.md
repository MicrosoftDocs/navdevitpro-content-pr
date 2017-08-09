---
title: "AppendLine Method"
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

# AppendLine Method
Appends a copy of the specified string followed by the default line terminator to the end of the current TextBuilder object. If this parameter is omitted, only the line terminator will be appended.  
```  
[Ok := ] TextBuilder.AppendLine([Text])  
```  
## Parameters
*Text*    
&emsp;Type: Text  
The string to append.  
  
## Return Value
*Ok*  
&emsp;Type: Boolean  
**True** if the operation was successful; otherwise, **false**.  
If you omit this optional return value and the operation does not execute successfully, a run-time error will occur.  
  
## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

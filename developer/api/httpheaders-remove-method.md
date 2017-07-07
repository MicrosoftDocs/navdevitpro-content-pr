---
title: "Remove Method"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 06/29/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 620f0e32-eadc-43e9-8f6e-8fc0b12c3aaf
caps.latest.revision: 9
manager: edupont
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# Remove Method
Removes the key and the related values from the HttpHeaders object.

```
[Ok := ] HttpHeaders.Remove(Key)
```

## Parameters
*HttpHeaders*  
&emsp;Type: HttpHeaders

*Key*  
&emsp;Type: Text

## Return Value
&emsp;Type: Boolean  
&emsp;**True** if key exists; **false** otherwise.

## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

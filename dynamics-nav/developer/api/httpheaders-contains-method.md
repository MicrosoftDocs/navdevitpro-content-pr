---
title: "Contains Method"
ms.author: solsen
ms.custom: na
ms.date: 12/13/2017
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

# Contains Method
Checks if an HttpHeaders contains a property with a given key.

```
Result := HttpHeaders.Contains(Key)
```

## Parameters
*HttpHeaders*  
&emsp;Type: [HttpHeaders](httpheaders-class.md)

*Key*  
&emsp;Type: [Text](/datatypes/devenv-text-data-type.md)

## Return Value
*Result*  
&emsp;Type: [Boolean](/datatypes/devenv-boolean-data-type.md)

&emsp;**True** if the object contains a property with the given key; otherwise, **false**.

## See Also
[HttpHeaders](httpheaders-class.md)  
[HTTP, JSON, TextBuilder, and XML API](../devenv-restapi-overview.md)  
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  
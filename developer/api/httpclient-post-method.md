---
title: "Post Method"
ms.author: solsen
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

# Post Method
Sends a POST request to the specified Uniform Resource Identifier (URI) as an asynchronous operation.

```
[Ok := ] HttpClient.Post(Path, Content, Reponse)
```

## Parameters
*Path*  
&emsp;Type: String

*Content*  
&emsp;Type: HttpContent

*Response*  
&emsp;Type: HttpResponseMessage

## Return Value
*Ok*  
&emsp;Type: Boolean  
&emsp;**True** if the operation was successful; otherwise, **false**.

Accessing the HttpContent property of HttpResponseMessage in a case when the request fails will result in an error.

## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

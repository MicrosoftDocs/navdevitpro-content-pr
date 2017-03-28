---
title: "Put Method"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 03/28/2017
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

# Put Method
Sends a PUT request to the specified Uri as an asynchronous operation.

```
[Ok := ] HttpClient.Put(Path, Content, Reponse)
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
&emsp;**true** if the operation was successful; otherwise, **false**.

Accessing the HttpContent property of HttpResponseMessage in case when the request failed will result in an error.

## See Also
[Getting Started](newdev-get-started.md)  
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)
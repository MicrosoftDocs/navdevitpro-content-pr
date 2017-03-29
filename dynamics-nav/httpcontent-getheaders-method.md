---
title: "GetHeaders Method"
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

# GetHeaders Method
Gets the content's Http headers.

```
[Ok := ] HttpContent.GetHeaders(Result)
```

## Parameters
*HttpContent*
&emsp;Type: HttpContent

*Result*
&emsp;Type: HttpHeaders

## Return Value
*Ok*
&emsp;Type: Boolean
&emsp;**true** if the operation was successful; otherwise, **false**. 

Accessing the HttpContent property of HttpResponseMessage in a case when the request fails will result in an error.

## See Also
[Getting Started](newdev-get-started.md)  
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)
---
title: "DefaultRequestHeaders Method"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 02/21/2017
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

# DefaultRequestHeaders Method
Gets the default request headers which should be sent with each request.

```
HttpHeaders := HttpClient.DefaultRequestHeaders
```

## Property Value
*HttpHeaders*
&emsp;Type: HttpHeaders

Since the headers variable is a reference type, when you add a header to it the default headers for the Http client from which the headers were gotten are changed.
You can not set some other HttpHeaders object as default headers, you have to update the one fetched from Http client.

## See Also
[Getting Started](newdev-get-started.md)  
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)
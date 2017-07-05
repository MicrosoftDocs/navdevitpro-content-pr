---
title: "HttpClient Class"
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

# HttpClient Class
Provides a base class for sending HTTP requests and receiving HTTP responses from a resource identified by a Uri.

The following methods are available on the HttpClient class.

|Method name|Description|
|-----------|-----------|
|[Clear](httpclient-clear-method.md)|Sets the HttpClient variable to the default value.|
|[DefaultRequestHeaders](httpclient-defaultrequestheaders-method.md)|Gets the default request headers which should be sent with each request.|
|[Delete](httpclient-delete-method.md)|Sends a DELETE request to delete the resource identified by the request URL.|
|[Get](httpclient-get-method.md)|Sends a GET request to get the resource identified by the request URL.|
|[GetBaseAddress](httpclient-getbaseaddress-method.md)|Gets the base address of Uniform Resource Identifier (Uri) of the Internet resource used when sending requests.|
|[Post](httpclient-post-method.md)|Sends a POST request to the specified Uri as an asynchronous operation.|
|[Put](httpclient-put-method.md)|Sends a PUT request to the specified Uri as an asynchronous operation.|
|[Send](httpclient-send-method.md)|Sends an HTTP request as an asynchronous operation.|
|[SetBaseAddress](httpclient-setbaseaddress-method.md)|Sets the base address of Uniform Resource Identifier (Uri) of the Internet resource used when sending requests.|
|[Timeout](httpclient-timeout-method.md)|Gets or sets the duration in seconds to wait before the request times out.|
|[AddCertificate](httpclient-addcertificate-method.md)|Adds a certificate to the HttpClient class.|

## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

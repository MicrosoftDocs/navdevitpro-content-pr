---
title: "HTTP, JSON, and XML API Reference"
description: "Overview of the API capabilities."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 06/01/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: SusanneWindfeldPedersen
caps.latest.revision: 18
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# HTTP, JSON, and XML API Overview
With the API for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] you have HTTP, JSON, and XML classes available for accessing services in the cloud. The following table shows the classes that are available.

## API reference

|Class|Description|
|-----|-----------|
|[HttpClient](api/httpclient-class.md)|Provides a base class for sending HTTP requests and receiving HTTP responses from a resource identified by a Uri.|
|[HttpContent](api/httpcontent-class.md)|A base class representing an HTTP entity body and content headers.|
|[HttpHeaders](api/httpheaders-class.md)|The HttpHeaders class contains a collection of headers and their values.|
|[HttpRequestMessage](api/httprequestmessage-class.md)|Represents an HTTP request message.|
|[HttpReponseMessage](api/httpresponsemessage-class.md)|Represents an HTTP response message.|
|[JsonArray](api/jsonarray-class.md)|JsonArray is a container for any well-formed JSON array. A default JsonArray contains an empty JSON array.|
|[JsonObject](api/jsonobject-class.md)|JsonObject object is a container for any well-formed JSON object. A default JsonObject contains an empty JSON object.|
|[JsonToken](api/jsontoken-class.md)|JsonToken object is a container for any well-formed JSON data. A default JsonToken contains the JSON value of NULL.|
|[JsonValue](api/jsonvalue-class.md)|JsonValue object is a container for any well-formed JSON object. A default JsonValue is set to the JSON value of NULL.|


## See Also
[Getting Started](devenv-get-started.md)  
[Developer Reference](devenv-reference-overview.md)
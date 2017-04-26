---
title: "Developer Reference"
description: "Overview of the objects."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/23/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: SusanneWindfeldPedersen
caps.latest.revision: 18
---

[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/newdev_dev_preview.md)]

# Developer Reference
This section describes all of the objects that are available with [!INCLUDE[navnow_md](includes/navnow_md.md)]. For additional reference and information, see [Objects](objects.md).

## Defining the data model
|To | See |
|---|-----|
|Learn about how to define new table objects for your extension.|[Table Object](newdev-table-object.md)|
|Learn about how to modify and extend existing table objects. |[Table Extension Object](newdev-table-ext-object.md)|

## Presenting the data
|To |See |
|---|----|
|Learn about how to create new page objects for your extension.|[Page Object](newdev-page-object.md)|
|Learn about how to modify and extend existing page objects. |[Page Extension Object](newdev-page-ext-object.md)|
|Learn about how to create report objects|[Report Object](newdev-report-object.md)|
|Learn about how to create xmlport objects|[XmlPort Object](newdev-xmlport-object.md)|
|Learn about how to create query objects|[Query Object](newdev-query-object.md)|

## Writing code
|To |See |
|---|----|
|Learn about writing codeunits for your extension.|[Codeunit Object](newdev-codeunit-object.md)|

## REST API
|Class|Description|
|-----|-----------|
|[HttpClient](httpclient-class.md)|Provides a base class for sending HTTP requests and receiving HTTP responses from a resource identified by a Uri.|
|[HttpContent](httpcontent-class.md)|A base class representing an HTTP entity body and content headers.|
|[HttpHeaders](httpheaders-class.md)|The HttpHeaders class contains a collection of headers and their values.|
|[HttpRequestMessage](httprequestmessage-class.md)|Represents an HTTP request message.|
|[HttpReponseMessage](httpresponsemessage-class.md)|Represents an HTTP response message.|
|[JsonArray](jsonarray-class.md)|JsonArray is a container for any well-formed JSON array. A default JsonArray contains an empty JSON array.|
|[JsonObject](jsonobject-class.md)|JsonObject object is a container for any well-formed JSON object. A default JsonObject contains an empty JSON object.|
|[JsonToken](jsontoken-class.md)|JsonToken object is a container for any well-formed JSON data. A default JsonToken contains the JSON value of NULL.|
|[JsonValue](jsonvalue-class.md)|JsonValue object is a container for any well-formed JSON object. A default JsonValue is set to the JSON value of NULL.|


## See Also
[Getting Started](newdev-get-started.md)  
[Tables](tables.md)  
[Pages](pages.md)

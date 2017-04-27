---
title: GET RetainedEarningsStatement method | Microsoft Docs
description: Gets a RetainedEarningsStatement.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/13/2017
ms.author: solsen
---

# GET RetainedEarningsStatement Method
Retrieve the properties and relationships of a RetainedEarningsStatement report object for [!INCLUDE[d365fin_long_md](../dynamics-nav/includes/d365fin_long_md.md)].

## HTTP request
```
GET /financials/companies/{id}/retainedEarningsStatement
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and RetainedEarningsStatement object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://graph.microsoft.com/beta/financials/companies/{id}/retainedEarningsStatement?$orderby=lineNumber&$filter=dateFilter ge 2019-01-01 and dateFilter le 2020-12-31
```

**Response**

Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "lineNumber": 20000,
  "display": "Net Income",
  "netChange": 23210.68,
  "lineType": "detail",
  "indentation": 0,
  "dateFilter": "2020-12-31"   
}
```


## See Also
[Microsoft Graph Reference](graph-reference.md)  
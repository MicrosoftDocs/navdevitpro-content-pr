---
title: Update unitsOfMeasure | Microsoft Docs
description: Updates a unit of measure object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# Update unitsOfMeasure
Update the properties of a units of measure object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../v1.0/endpoints-apis-for-dynamics.md).

```
PATCH businesscentralPrefix/companies({id})/unitsOfMeasure({id})
```

## Request headers

|Header|Value|
|------|-----|
|Authorization |Bearer. Required.|
|Content-Type  |application/json|
|If-Match      |Required. When this request header is included and the eTag provided does not match the current tag on the **unitsOfMeasure**, the **unitsOfMeasure** will not be updated. |

## Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

## Response
If successful, this method returns a ```200 OK``` response code and an updated **unitsOfMeasure** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
PATCH https://{businesscentralPrefix}/api/v1.0/companies({id})/unitsOfMeasure({id})
Content-type: application/json

{
  "displayName": "One Piece"
}
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "id-value",
  "code": "PCS",
  "displayName": "One Piece",
  "internationalStandardCode": "EA",
  "lastModifiedDateTime": "2017-03-15T01:21:09.563Z"
}
```


## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)  

[Units of Measure](../resources/dynamics_unitsofmeasure.md)  
[Get Units of Measure](../api/dynamics_unitsofmeasure_get.md)  
[Create Units of Measure](../api/dynamics_create_unitsofmeasure.md)  
[Delete Units of Measure](../api/dynamics_unitsofmeasure_delete.md)  
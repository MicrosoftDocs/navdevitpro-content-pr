---
title: Get subscriptions | Microsoft Docs
description: Gets a subscriptions object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/03/2018
ms.author: solsen,henrikwh
ROBOTS: NOINDEX
---

# Get subscriptions
Retrieves the properties of webhook subscription objects for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../api-reference/v1.0/endpoints-apis-for-dynamics.md).
```
GET businesscentralPrefix/subscriptions
```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a `200 OK` response code and a **subscription** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
https://{businesscentralPrefix}/api/beta/subscriptions 
```

**Response**

Here is an example of the response. 

> [!NOTE]  
> The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "subscriptionId": "c670ea73cacb459bb51dc1740da2f1db",
  "notificationUrl": "https://contoso.com/myCallbacks",
  "resource": "/api/beta/companies(f64eba74-dacd-4854-a584-1834f68cfc3a)/customers",
  "userId": "00000000-0000-0000-0000-000000000001",
  "lastModifiedDateTime": "2018-10-12T12:32:35Z",
  "clientState": "anytextvalueof2048",
  "expirationDateTime": "2018-10-15T12:32:35Z"
}
```


## See also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Subscription Resource Type](../resources/dynamics_subscription.md)  
[Create subscriptions](dynamics_subscription_create.md)  
[Update subscriptions](dynamics_subscription_update.md)  
[Delete subscriptions](dynamics_subscription_delete.md)  
[Microsoft REST API Guidelines](https://github.com/Microsoft/api-guidelines/blob/vNext/Guidelines.md#15-push-notifications-via-webhooks)
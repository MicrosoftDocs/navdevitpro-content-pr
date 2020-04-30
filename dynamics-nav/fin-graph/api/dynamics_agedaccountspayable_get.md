---
title: Get agedAccountsPayable | Microsoft Docs
description: Gets an aged accounts payable object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: solsen
ROBOTS: NOINDEX
---

# Get agedAccountsPayable
Retrieve the properties and relationships of an aged accounts payable report object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request
Replace the URL prefix for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] depending on environment following the [guideline](../../api-reference/v1.0/endpoints-apis-for-dynamics.md).
```
GET businesscentralPrefix/companies({id})/agedAccountsPayable
```

## Request headers

|Header        |Value                     |
|--------------|--------------------------|
|Authorization |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and an **agedAccountsPayable** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://{businesscentralPrefix}/api/beta/companies({id})/agedAccountsPayable
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "vendorId": "id-value",
  "vendorNumber": "50000",
  "name": "Nod Publishers",
  "currencyCode": "USD",
  "balanceDue": 17273.87,
  "currentAmount": 0,
  "period1Amount": 0,
  "period2Amount": 0,
  "period3Amount": 17273.87,
  "agedAsOfDate": "2019-01-01",
  "periodLengthFilter": "3M"  
}
```


## See also
[Tips for working with the APIs](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips)  
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Dynamics 365 Business Central](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Aged Accounts Payable](../resources/dynamics_agedaccountspayable.md)  
[Get Aged Accounts Receivable](../api/dynamics_agedaccountsreceivable_get.md)  
[Account](../resources/dynamics_account.md)  

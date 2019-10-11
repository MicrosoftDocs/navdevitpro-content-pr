---
title: Moving from beta to v1.0 | Microsoft Docs
description: Changes from the beta version of the APIs to the v1.0 of the APIs in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/03/2019
ms.author: solsen
---

# Moving from Beta to v1.0
With the April'19 release of [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)], the Standard APIs were released in version 1.0.  

API version numbers are mananged in the URI `https://api.businesscentral.dynamics.com/v2.0/{environment name}/api/{API VERSION}/`. For example, for v1.0 of the API the URI is `https://api.businesscentral.dynamics.com/v2.0/production/api/v1.0/`.

> [!IMPORTANT]  
> The beta API will remain live until April 2020. It's recommended to move to v1.0 as soon as possible. When moving from **beta** to **v1.0**, pay attention to changes related to URIs of the document APIs, and to the customer APIs where balance, overdueAmount, and totalSalesExcludingTax have moved to the customerFinancialDetails API. Other changes are additive.  

Comparing [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] **beta** API, to [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] **v1.0** APIs have the following changes.

|Entity | Changes|
|-------|--------|
|customer|Properties balance, overdueAmount, totalSalesExcludingTax have moved to a new entity customerFinancialDetails, which has a relation to the customer entity.|
|customerFinancialDetails|Entity added.|
|companyInformation |bussinessProfileId has been removed.|
|salesInvoice, salesOrder, salesQuote|Biling, shipping and selling postal addresses are added.|
|purchaseInvoice|buyFrom, payTo and shipTp adesses added.|
|salesInvoiceLine, salesOrderLine, salesQuoteLine, salesCreditMemoLine, purchaseInvoiceLine|Key changed from multipart key, to a single key. Type has changed from Guid to String.|
|salesCreditMemo|Billing and selling addresses added, and properties phoneNumber and email.|
|journalLine|Added attachment, so attachments can be added to journalLine".|
|timeRegistrationEntry|New entity. Makes it possible to add employee time registrations.|
|salesQuote|Properties phoneNumber and email have been added.|

For a full comparison of API versions, compare the metadata of the APIs. Using OAuth, tenant ID is not needed in the URI when querying:

```json 
GET https://api.businesscentral.dynamics.com/v1.0/api/beta/$metadata
GET https://api.businesscentral.dynamics.com/v1.0/api/v1.0/$metadata
```
Using Basic Auth:

```json 
GET https://api.businesscentral.dynamics.com/v1.0/{tenant Id}/api/v1.0/$metadata
```
## See Also
[Welcome to the API(v1.0) for Dynamics 365 Business Central](index.md)  
[Endpoints for the APIs](endpoints-apis-for-dynamics.md)  
---
title: "DataClassification Property"
ms.author: jswymer
ms.custom: na
ms.date: 01/05/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
author: jswymer
---

# DataClassification Property
Sets the classification of the data in the table or field. The data classification can be used to adhere to security, compliance, and privacy requirements or processes for collecting, storing, and using data and personal information.  

## Applies to  

-   Table objects
-   Table field controls

## Property Values  
|Value|Description|  
|---------------|---------------------|  
|CustomerContent|Data that users provide to, transfer in, store in, or process in.|  
|EndUserIdentificationInformation|Data that directly identifies or could be used to identify the authenticated user. This does not contain C1 admin data. EUII does not extend to other personal information found in Customer Content (e.g. contact lists are Customer Content), contact lists are Customer Content).   Note: C1 admin data is Account Data. Data about unauthenticated C2 users is Customer Content. |  
|AccountData|Contact and billing/purchase/payment/license information for the C1 enterprise, including the C1 admin and any C1 subdelegated admins. Note that C1 user data is EUII and C2 user data is Customer Content.|  
|EndUsePseudonymousIdentifiers|An identifier created by Microsoft tied to the C1 or C2 user of a Microsoft service.  When EUPI is combined with other information (such as a mapping table), it identifies the end user.   Note that EUPI does not contain information uploaded or created by the customer (Customer Content or EUII). |
|OrganizationIdentifiableInformation|Time|  
|SystemMetadata|Data generated in the course of running the service, not linkable to a user or tenant.  Does not contain Access Control Data, Customer Content, EUII, Suppport Data, Account Data, Public Personal Data, EUPI, or OII.|  


## Remarks  
This property is used together with the APPLICATIONAREA function to hide user interface elements.  
  
## See Also
[TextBuilder](textbuilder-class.md)  
[HTTP, JSON, TextBuilder, and XML API](../devenv-restapi-overview.md)  
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

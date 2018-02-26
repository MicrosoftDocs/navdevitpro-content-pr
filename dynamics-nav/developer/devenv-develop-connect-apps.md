---
title: "Developing Connect Apps for Dynamics 365 Business Central"
author: SusanneWindfeldPedersen
ms.author: solsen
ms.custom: na
ms.date: 02/26/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Developing Connect Apps for Dynamics 365 Business Central

1. Sign up for a [Dynamics 365 Business Central sandbox]().  
For exploring and prototyping with the APIs, use basic authentication with the tenant specific endpoint https://api.financials.dynamics.com/v1.0/<tenant user domain url>/api/beta. You can set up basic authentication by creating a **Web Service Access** key in Dynamics 365 Business Central. 
2. Log into your tenant, in Search, enter **Users** and then select the relevant link.
3. On the **Users** page, in the **Web Service Access Key** field, generate a key.  
4. Copy the generated key and use it as the password for the username. <!-- (add link from getting started with APIs)  -->

>[!IMPORTANT]  
> For developing and going into production, you must, however, use Azure Active Directory (AAD)/OAuth v2 authentication and the common endpoint https://api.financials.dynamics.com/v1.0/api/beta. 
 
For more information, see the preview of the [API documentation](../fin-graph/resources/dynamics_overview.md).

Download an API explorer, such as Postman or Fiddler to connect to and explore the API. See examples in below video. 

## See Also

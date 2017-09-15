---
title: "Developing Connect Apps for Dynamics 365 for Financials"
author: SusanneWindfeldPedersen

ms.author: solsen
ms.custom: na
ms.date: 09/15/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Developing Connect Apps for Dynamics 365 for Financials
A Connect app establishes a connection between two independent services using an API to interchange data. A typical example of a Connect app is a Payroll solution. All work related to Payroll is done within your payroll service and only as a last step is the financial data posted into [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] using the API. A Connect app is mainly created using common development tools and the REST API’s made available in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)].

## Want to try it out?
With this preview, you can get started exploring the APIs that we offer for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. We do not yet support submission to AppSource, so for now, we encourage you to get familiar with the structure and possibilities of the API.

It's easy to get started. Just spin up a tenant by going through these steps.

1) Sign up for [Dynamics 365 for Financials](https://signup.microsoft.com/signup?sku=6a4a1628-9b9a-424d-bed5-4118f0ede3fd&ru=https%3A%2F%2Fportal.financials.dynamics.com).    
2) To connect to your tenant via APIs, you can use your tenant URL and basic authentication.    
    1) The tenant's API endpoint is the tenant's base URL (up until .com) followed by `:7048/MS/api/beta/`, for example, `https://cronus.financials.dynamics.com:7048/MS/api/beta/`.  
    2) To set up basic authentication, create a Web Service Access key in [!INCLUDEd365fin_md]. On the **Users** page, in the **Web Service Access Key** field, generate a key.

   > [!NOTE]
   > For production, you should use Azure Active Directory (AAD) for authentication and the common service endpoint `https://api.financials.dynamics.com/v1.0/api/beta`. However, for exploring and prototyping with the API's, using basic authentication and the tenant URL as described will be faster.

3) Go to the documentation on the APIs, you can get our published preview [here](https://msdn.microsoft.com/en-us/dynamics-nav/fin-graph/index).  
4) Download an API explorer, such as [Postman](https://www.getpostman.com/) or [Fiddler](http://www.telerik.com/fiddler) to connect to and explore the API.

### Some tips for working with the API's

+ Call (GET) the endpoint to list all the API
+ Call (GET) the endpoint with `$metadata` to list all metadata for the API
+ Calling a resource API (GET) will return a list of all instances of the resource type
+ Each resource is uniquely identified through an ID, see the following example:  

```
{
    "@odata.context": "<endpoint>/$metadata#companies",
    "value": [
        {
            "id": "bb6d48b6-c7b2-4a38-9a93-ad5506407f12",
            "systemVersion": "18453",
            "name": "CRONUS USA, Inc.",
            "displayName": "CRONUS USA, Inc.",
            "businessProfileId": ""
        }
    ]
}

```

+ The resource ID must be provided in the URL when trying to read or modify a resource or any of its children. The ID is provided in () after the API endpoint. For example, to GET the “CRONUS USA, Inc.” company details, you must call `<endpoint>/companies(bb6d48b6-c7b2-4a38-9a93-ad5506407f12)/`
+ All resources live in the context of a parent company, which means that the company ID must be provided in the URL for all resource API calls. For example, to GET all customers in the “CRONUS USA, Inc.” company, you must call `<endpoint>/companies(bb6d48b6-c7b2-4a38-9a93-ad5506407f12)/customers`
+ You can provide filters in API calls. The syntax for this follows the [Microsoft REST API guidelines](https://github.com/Microsoft/api-guidelines/blob/master/Guidelines.md#97-filtering). For example, to GET all open (unpaid) sales invoices above 1000.00 excl tax, call `<endpoint>/companies(bb6d48b6-c7b2-4a38-9a93-ad5506407f12)/salesInvoices?$filter=status eq 'Open' and totalAmountExcludingTax gt 1000.00`

## See Also
[Working with Dynamics 365 for Financials in Microsoft Graph](../fin-graph/resources/dynamics_overview.md)  

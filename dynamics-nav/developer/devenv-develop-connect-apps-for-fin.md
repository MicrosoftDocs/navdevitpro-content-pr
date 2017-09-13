---
title: "Developing Connect Apps for Dynamics 365 for Financials"
author: SusanneWindfeldPedersen

ms.author: solsen
ms.custom: na
ms.date: 09/11/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Developing Connect Apps for Dynamics 365 for Financials
A Connect app establishes a connection between two independent services using an API to interchange data. A typical example of a Connect app is a Payroll solution. All work related to Payroll is done within your payroll service and only as a last step is the financial data posted into [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] using the API. A Connect app is mainly created using common development tools and the REST API’s made available in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. REST API's can be used in combination with an extension as well, for example, to enable setup and configuration.

## Want to try it out?
With this preview, you can get started on exploring the APIs that we offer for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. We do not yet support submission to AppSource, so for now, we encourage you to get familiar with the structure and possibilities of the API.

It's easy to get started. Just spin up a sandbox environment by going through these steps.

1) Sign up for a [Dynamics 365 for Financials sandbox](https://aka.ms/GetSandboxForFinancials).    
2) Set up basic authentication by achieving a Web Service Access key in [!INCLUDE[d365fin_md](includes/d365fin_md.md)]. On the **Users** page, in the **Web Service Access Key** field, generate a key.
   > [!NOTE]
   > For authentication, Azure Active Directory (AAD) should be used. However, for exploring and prototyping with the API's, using basic authentication as described will be faster.

3) Go to the documentation on the APIs, you can get our published preview [here](https://msdn.microsoft.com/en-us/dynamics-nav/fin-graph/index).
4) Download an API explorer, such as [Postman](https://www.getpostman.com/) or [Fiddler](http://www.telerik.com/fiddler) to explore the API.

### Some tips for working with the API's

+ Use the endpoint `https://api.financials.dynamics.com/v1.0/api/beta/` to list all the API
+ Use the endpoint `https://api.financials.dynamics.com/v1.0/api/beta/metadata` to list all metadata for the API
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
        },
    ]
}

```
+ The resource ID must be provided in the URL when trying to read or modify a resource or any of its children. The ID is provided in () after the API endpoint. For example, to GET the “CRONUS USA, Inc.” company details, you must call `<endpoint>/companies(bb6d48b6-c7b2-4a38-9a93-ad5506407f12)/`
+ All resources live in the context of a parent company, which means that the company ID must be provided in the URL for all resource API calls. For example, to GET all customers in the “CRONUS USA, Inc.” company, you must call `<endpoint>/companies(bb6d48b6-c7b2-4a38-9a93-ad5506407f12)/customers`
+ You can provide filters in API calls. The syntax for this follows the [Microsoft REST API guidelines](https://github.com/Microsoft/api-guidelines/blob/master/Guidelines.md#97-filtering). For example, to GET all open (unpaid) sales invoices above 1000.00 excl tax, call `<endpoint>/companies(bb6d48b6-c7b2-4a38-9a93-ad5506407f12)/salesInvoices?$filter=status eq 'Open' and totalAmountExcludingTax gt 1000.00`

## See Also
[Working with Dynamics 365 for Financials in Microsoft Graph](../fin-graph/resources/dynamics_overview.md)  

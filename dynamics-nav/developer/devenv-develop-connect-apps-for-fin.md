---
title: "Developing Connect Apps for Dynamics 365 for Financials"
ms.custom: na
ms.date: 09/11/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 471299b6-82cd-41cc-b529-8b60ece530a5
caps.latest.revision: 5
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Developing Connect Apps for Dynamics 365 for Financials
A Connect app establishes a connection between two independent services using an API to interchange data. A typical example of a Connect app is a Payroll solution. All work related to Payroll is done within your service and only as a last step is the financial data posted into [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] using the API. A Connect app is mainly created using common development tools, REST API’s, and the API’s made available in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. When needed a Connect app in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] can have a single page or two created as an extension used for setup, configuration or to support for example an import scenario.

## Want to try it out?
With this preview, you can get started on exploring the APIs that we offer for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. We do not yet support submission to AppSource and Licensing, so for now, we encourage you to get familiar with the structure and possibilities of the API.

It's easy to get started. Just spin up a sandbox environment by going through these steps.

1) Sign up for a [Dynamics 365 for Financials sandbox](https://aka.ms/GetSandboxForFinancials).    
2) Set up basic authentication by achieving a Web Service Access key in [!INCLUDE[d365fin_md](includes/d365fin_md.md)]. On the **Users** page, in the Web Service Access Key field, generate a key.
    > [!NOTE]
    > Authentication will happen through AAD when the APIs are no longer in preview.
3) Go to the documentation on the APIs, you can get our published preview [here](https://msdn.microsoft.com/en-us/dynamics-nav/fin-graph/index).
4) Download an API explorer, such as [Postman](https://www.getpostman.com/) or [Fiddler](http://www.telerik.com/fiddler) to explore the API.

### Some more tips for getting started
+ All API calls are in the context of `company`
+ To filter on data, use the following syntax
+ api/companies ("id")
+ Use the endpoint https://api.financials.dynamics.com/v1.0/api/beta/ to list all the API
+ Use the endpoint https://api.financials.dynamics.com/v1.0/api/beta/metadata to list all metadata for the API

## Questions?
This [FAQ](https://go.microsoft.com/fwlink/?linkid=841520) responds to the most common questions you might have about apps for Dynamics 365 for Financials. If you have further questions, don't hesitate to [email us](mailto:d365val@microsoft.com).

## Need help?
If you would like some coaching, you can contact an app subject matter expert from the following list:  
•	[Cloud Ready Software](http://cloud-ready-software.com)    
•	[Dynamics App Alliance](http://dynamicsappalliance.com)

Partners in this list:

•	Are listed alphabetically  
•	Are assisting or have assisted a minimum of three partners with bringing apps into Microsoft AppSource  
•	Have a packaged service available (and listed on their website) about the app guidance that they provide  

If you believe you should be listed as an app service partner, don't hesitate to [reach out to us](mailto:d365val@microsoft.com).
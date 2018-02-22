---
title: "Connect Apps"
description: ""
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 02/20/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.author: solsen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

# Connect Apps

## What is a Connect app? 
A Connect app establishes a point-to-point connection between Dynamics 365 Business Central and your service offering using a standard REST API to interchange data. Any coding language capable of calling REST APIs can be used to develop your Connect app.  

<!-- INSERT VIDEO:  
Objective: Introucing Connect Apps + Business value 
New video that needs to be created -->
 
## How can I benefit from offering a Connect app? 
Online service offerings like payroll, expense management, web-shops, project planning etc. typically have many connection points. Connect apps allows you to make connections between those online service offerings and your business solution. This connection can be achieved on a data level without needing to do development. Therefore, reusing those connection points provide you with an opportunity to reuse your investments from REST integrations with other Cloud Services. 
Optionally, you can build an interface in Dynamics 365 Business Central, which determines how your data needs to flow between Dynamics 365 Business Central and your online service offering.  

## Examples of Connect apps 
Below you can find some examples of online services, which could benefit from being integrated to Dynamics 365 Business Central using Connect apps: 
- Payroll – Read chart of accounts, synchronizing employee information and push payroll transactions to the Dynamics 365 Business Central Ledger 
- Bank integration – Make payments from within your business solutions towards your bank. 
- Expenses – Collect and reconcile transactions in well-adopted expense apps. 
- Web-shops – Synchronize items, customers and other entities to create sales orders and invoices. 
- Financial Services – Read financial data and provide value added services such as funding and loans. 

## How do I develop a Connect App?
Dynamics 365 Business Central offers many APIs that you can call from within your preferred coding language. 
Prior to publishing your app you can try out and develop against the APIs using a trial tenant: 
1. Sign up for Dynamics 365 for Finance and Operations, Business edition ((Business Central). 
2. When exploring and prototyping the APIs, the easiest is to use basic authentication with the tenant specific endpoint https://api.financials.dynamics.com/v1.0/<tenant user domain url>/api/beta. 
    - To set up basic authentication, create a Web Service Access key in Dynamics 365. Log into your tenant, search for and open the Users page, and in the Web Service Access Key field, generate a key. Copy this, and use as the password for the username. 
    - For developing and production, you must, however, use Azure Active Directory (AAD)/OAuth v2 authentication and the common endpoint https://api.financials.dynamics.com/v1.0/api/beta. 
3. Go to the documentation on the APIs, you can get our published preview [here](). 
4. Download an API explorer, such as Postman or Fiddler to connect to and explore the API. See examples in below video. 
 
<!-- INSERT VIDEO: 
HDI – V6 – Use APIs from a Connect App -->
 
You can now develop the integration using your favorite development tool. 

## How do I get my Connect app published in AppSource?  
To ease your journey, from the initial idea submission to the final publication, we have created a guide that you can lean on throughout the process of bringing your Connect app to Microsoft AppSource. The guide consists of 3 documents that outlines all the steps that must be taken to get your app to go live on the platform. You need to complete the steps in the given order to pass the different validation stages and getting your app published on AppSource (see steps below): 
Get the prerequisites in place & Develop the technical aspects of your Connect app  
Needs to be build (combo of original doc 1. and 2.1) 
Develop the marketing aspects of your app 
Publish your app. 
 
Learn more about each step here: [aka.ms/BusinessCentralApps](). 
 
<!-- INSERT VIDEO:  
Ojective: “Publish a Connect app” 
New video that needs to be created --> 
 
## Where do I learn more about Connect apps? 
To learn more about how to develop Connect apps, select the following links:  
- Documentation on REST APIs 
- Getting started with connect apps  
- Overview of connection endpoints and authentication options 
- Link to blogpost – haven’t been created yet  [Symbol] NOTE: waiting on input from Peter  
- If your Connect app requires a specific set up in Dynamics 365 Business Central, then you have the opportunity to add objects. In this case you will have to follow the guide on developing Add-on apps in combination with using the Connect API. Find the guide on how to develop Add-on apps here.  
 
To learn more about Connect apps in general, select the following links:  
- FAQ on Connect apps <!--  – needs to be created -->
- Best Practices (Connect apps) <!--  – needs to be created -->




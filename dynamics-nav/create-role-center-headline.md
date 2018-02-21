---
title: "Create a Role Center Headline"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
author: jswymer
---
# Create a Role Center Headline

You can set up a Role Center to display a series of headlines that can provide the user with up-to-date information and insight into the business and daily work. For example, typical categories for headlines could include:

-   My performance
-   My workday 
-   Organizational health,  
-   Productivity tips 
-   Cross-tenant insights (gamification, performance relative to peers) 
-   Getting started 
 

##  <a name=""></a> w Headlines Work

## n development
Headline headlines is a table object, where each field defines the content of a specific headline. The headlines are displayed by adding a HeadlinePart page to the Role Center. The source of this page it headline table. 

## In the Client 
The Role Center will display the first headline for 5 seconds, then display the next headline for 5 seconds, and so on. When it cycles through all headlines, it will start again.

The user can manually switch among headlines by selecting the dots (ooo).

The user can personalize their Role Center to show or hide headline part.

As an administrator, you can  by using Person


Create a In the client, the  

1. Create a table that for the headlines.

    Add field for each headline that you want to display, and add logic/code to calculate/generate the headlines.

2. Create a page for displaying that has the pagetype set to HeadlinePart

The source of a headline is a table field.   
 The implementation of a Cue involves the following elements:  
  
-   A table object with a field that holds the data that is contained in the Cue at runtime.  
  
-   A page object that contains the table field and displays the Cue in the [!INCLUDE[navnow](includes/navnow_md.md)] client.  
  
-   Logic that calculates the data to display in the Cue at runtime.  
  
     The logic can consist of a combination of C/AL and [!INCLUDE[navnow](includes/navnow_md.md)] objects, such as tables, queries, and codeunits. How and where you implement the logic will depend on whether the Cue is based on a FlowField or Normal field and what you want to achieve. 


> [!IMPORTANT]  
>  If ACS authentication is not available, consider creating at least one user who will be able to connect by using a [!INCLUDE[navnow](includes/navnow_md.md)] client. For example, if users are registered by using a certain ACS namespace and that namespace changes, then the users will no longer be able to connect.  
>   
>  One way to prevent this kind of lockout is to create a user who will be able to access the client using **NavUserPassword** authentication. For more information, see [Users and Credential Types](Users-and-Credential-Types.md). Another option is to create an ACS user but to never log that user in with ACS authentication, so that the user's ACS status remains **Pending**.  
>   
>  For either option, make sure that you assign the SUPER permission set to this user, to make sure that there is at least one user with full access to all client functionality.


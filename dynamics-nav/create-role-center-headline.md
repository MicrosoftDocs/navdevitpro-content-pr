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

You can set up a Role Center to display a series of headlines, where headlines appear one at a time for a predefined period of time. The headlines can provide users with up-to-date information and insight into the business and daily work. Typical categories of headlines could include:

-   My performance
-   My workday 
-   Organizational health,  
-   Productivity tips 
-   Cross-tenant insights (gamification, performance relative to peers) 
-   Getting started 
 
Headlines will only appear in the [!INCLUDE[navnow](includes/navnow_md.md)]; they will be hidden on all client types.

##  <a name=""></a>Design concept

### In development
Headlines are displayed by using a **HeadlinePart** type page. Each individual headline is defined by a field on the page. The source for this field can be a field in an underlying table or an expression.

-   The HeadlinePart page is designed for Role Centers, in other words, pages that have the page type **RoleCenter**. If you use a **HeadlinePart** page on another page type, the part will not render in the client.

-   Headlines can be made interactive by using the OnDrillown trigger or DrillDown property on fields. This makes it possible for users to dig deeper into numbers or values that are shown in the headline or link to another page or URL, like online Help. users to select the headline and be taken somewhere else. 

    For example, by using the OnDrillDown trigger, you 
-   You can stop an individual headlines by setting the Visible property on the field. 

## In the Client 
The Role Center will start by displaying the first headline that is defined on the Headline part page. The headline will appear for 5 seconds, then the next headline will appear for 5 seconds, and so on. When all the headlines have been displayed, it will cycle back to the first headline and continue from there.

If a headline is interactive, the user can select s can 

The user can manually switch among headlines by selecting the dots (ooo).

User can personalize their Role Center to show or hide Headline part.

As an administrator, you can  by using Person


## Create headline   

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


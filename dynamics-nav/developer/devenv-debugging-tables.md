---
title: "Viewing Table Data in Browser"
description: "View tables in browser for troubleshooting"
author: jswymer
ms.custom: na
ms.date: 03/01/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.author: jswymer
---

# Viewing Table Data by Using the Client
For developing and troubleshooting| it can be useful to view and inspect records and data in tables of the tenant database. To accommodate this| you can run a table object in the [!INCLUDE[d365fin_short_md](includes/d365fin_short_md.md)] Web client| which you can do directly from the browser or from your Visual Studio project. 

In the client| the table is read-only| so modifications cannot be made.

## Required permissions
Whether running the table directly from the client or from Visual Code| your [!INCLUDE[d365fin_short_md](includes/d365fin_short_md.md)] user account must have the following permissions:

-   Read permission on the table that you want to run.
-   Execution permission (direct) on the System object **1350 Run table**.

For information about assigning permissions| see [Manage Users and Permissions](https://docs.microsoft.com/en-US/dynamics365/financials/ui-how-users-permissions).
 
## Run a table object directly from the client
To run table| add `&table=<TableID>` to the client's address (URL); replacing `<TableID>` with the ID of the table that you want to run.

For example| to run table **18 Customer**| you could use the following URL:

```
https://www.microsoft.com/en-US/dynamics365/financials/ui-how-users-permissions&table=18

```

## Run a table object from Visual Code project
<!--
U
sers: 
Must have read access to the table 
Must have execute permission on the Run Table System object 
Developers: 
Can only run a table through the web client so they require the same permissions 
Can set StartupObjectId to the ID of the table they want to inspect and StartupObjectType to "Table" and press Ctrl+F5 from VSCode to open the page. 
 
Append '?AID=FIN&table={YourTableId}'    
 
Limitations: 
By design: Nobody can access Internal tables, independent of permissions 
Known limitation: Viewing and scrolling through large tables has bad performance characteristics. 

-->
## Constraints
You cannot view the following system tables:

|  |Configuration Package File|
|  |Data Sensitivity|
|  |Debugger Breakpoint|
|  |Debugger Watch|
|  |Device|
|  |Document Service|
|  |Entitlement Set|
|  |Entitlement|
|  |MediaSet|
|  |Media|
|  |Membership Entitlement|
|  |Nav App Capabilities|
|  |Nav App Data Archive|
|  |Nav App Dependencies|
|  |Nav App Object Metadata|
|  |Nav App Objec tPrerequisites|
|  |Nav App Resource|
|  |Nav App Tenan tApp|
|  |Nav App|
|  |Object Metadata|
|  |Object Tracking|
|  |Object|
|  |PageDocumentation|
|  |Profile Page Metadata|
|  |Report Layout|
|  |Send To Program|
|  |Server Instance|
|  |Style Sheet|
|  |Token Cache|
|  |Upgrade Blob Storage|
|  |User Property|
|  |Web Service|
|  |Webhook Notification|
|  |Webhook Subscription|


## See Also  
[Developing Extensions](devenv-dev-overview.md)  


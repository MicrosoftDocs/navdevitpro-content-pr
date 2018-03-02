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

# Viewing Table Data
For developers, administrators, and support personnel, it can be useful to view and inspect records and data in tables of the tenant database, particularly when debugging or troubleshooting. To support this need, you can view table objects in the [!INCLUDE[d365fin_md](includes/d365fin_md.md)] Web client.

-   In a production environment, administrators and support can view a table directly from the client by appending the URL in the browser. 

-   In a development environment, in addition to viewing a table directly from the client, developers can view a table automatically when they publish/debug an AL project from Visual Studio. 

> [!NOTE]
> The table appears as read-only in the client, so modifications cannot be made.

> [!IMPORTANT]
> Data in the tables can be sensitive. Be sure to follow your organization's guidelines for handling such data. 

## Required permissions
Whether viewing the table directly from the client or from Visual Code, your [!INCLUDE[d365fin_md](includes/d365fin_md.md)] user account must have the following permissions:

-   Read permission on the table that you want to view.
-   Execution permission (direct) on the System object **1350 Run table**.

For information about assigning permissions, see [Manage Users and Permissions](https://docs.microsoft.com/en-US/dynamics365/financials/ui-how-users-permissions).
 
## View a table object directly from the client
To view a table, you add the `&table=<TableID>` to the client's address (URL), replacing `<TableID>` with the ID of the table that you want to see.

For example, if the URL is `https://dynamics.businesscentral.com`, then to view table **18 Customer**, you would use the following URL:

```
https://dynamics.businesscentral.com/?&table=18

```

Or for a specific company, such as "CRONUS Inc.":

```
https://dynamics.businesscentral.com/?company=CRONUS%20Inc.&table=18

```

<!--
Notice the use of `&` when `table=<TableID>` is located within the query string after the domain name.
-->


## View a table object from an AL project in Visual Studio
You can configure an AL project to view a table when you publish or debug the project (pressing F5 or Ctrl+F5). 

In the `launch.json` file for the project, set the `"startupObjectType"` parameter to `"table"` and the `"startupObjectId"` parameter to the ID of the table. For example:

```
{
    "version": "1.0.0",
    "configurations": [
        {
            "type": "al",
            "request": "launch",
            "name": "Publish to Microsoft cloud sandbox",
            "serverInstance": "dynamics",
            "startupObjectType": "table"
            "startupObjectId": 18
        }
    ]
} 

```

For more information about the `launch.json` file, see [Launch.json file](devenv-json-files.md#Launchjson).
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
You cannot view virtual tables or the following system tables:

|  ID  |  Name  |
|------|--------|
| 2000000170 |Configuration Package File|
| 2000000170 |Configuration Package File|
| 2000000173 |Data Sensitivity|
| 2000000100 |Debugger Breakpoint|
| 2000000103 |Debugger Watch|
| 2000000130 |Device|
| 2000000114 |Document Service|
| 2000000190 |Entitlement Set|
| 2000000191 |Entitlement|
| 2000000180 |MediaSet|
| 2000000181 |Media|
| 2000000195 |Membership Entitlement|
| 2000000162 |Nav App Capabilities|
| 2000000152 |Nav App Data Archive|
| 2000000161 |Nav App Dependencies|
| 2000000150 |Nav App Object Metadata|
| 2000000163 |Nav App Object Prerequisites|
| 2000000142 |Nav App Resource|
| 2000000151  |Nav App TenantApp|
| 2000000160 |Nav App|
| 2000000071 |Object Metadata|
| 2000000079 |Object Tracking|
| 2000000001 |Object|
| 2000000198 |Page Documentation|
| 2000000186 |Profile Page Metadata|
| 2000000082 |Report Layout|
| 2000000065 |Send To Program|
| 2000000112 |Server Instance|
| 2000000066 |Style Sheet|
| 2000000197 |Token Cache|
| 2000000081 |Upgrade Blob Storage|
| 2000000121 |User Property|
| 2000000076 |Web Service|
| 2000000194 |Webhook Notification|
| 2000000199 |Webhook Subscription|

## See Also  
[Developing Extensions](devenv-dev-overview.md)  


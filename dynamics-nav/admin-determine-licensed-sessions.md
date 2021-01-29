---
title: Determine the number of licensed sessions
description: Learn how to determine the number of licensed sessions.
author: edupont04
ms.reviewer: edupont
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.author: edupont
ms.date: 10/22/2020
---
# Determine the Number of Licensed Sessions in a Dynamics NAV Deployment

This article describes how to determine the number of sessions for which you are licensed in [!INCLUDE [navnow_md](includes/navnow_md.md)]. The article was first published on CustomerSource and is now ported to the Docs.microsoft.com site.

## Session Types

Two types of sessions exist in [!INCLUDE [navnow_md](includes/navnow_md.md)]:

1. User sessions
Used by users to log into [!INCLUDE [navnow_md](includes/navnow_md.md)] 
2. Application Server sessions
Used by the [!INCLUDE [navnow_md](includes/navnow_md.md)] Application Server 

> [!NOTE]
> Application server sessions cannot be used by users to log into [!INCLUDE [navnow_md](includes/navnow_md.md)].

You can determine the number of sessions for which you are licensed from one of the following resources:

1. License Information in the [!INCLUDE [nav_dev_short_md](includes/nav_dev_short_md.md)]
2. Licensed Sessions in [!INCLUDE [navnow_md](includes/navnow_md.md)]

## License Information in [!INCLUDE [nav_dev_short_md](includes/nav_dev_short_md.md)]

You can determine how many sessions you are licensed for in the **License Information** window in [!INCLUDE [nav_dev_short_md](includes/nav_dev_short_md.md)].

To access **License Information** in [!INCLUDE [nav_dev_short_md](includes/nav_dev_short_md.md)], go to **Tools**, **License Information**.

In **License Information**, you can find the number of user sessions and application server sessions you are licensed for by looking at the granules that are described

|Session type  |License type  |Granule  |
|---------|---------|---------|
|User sessions     |BRL License - Business Essentials  | * Granule 1200 - NFR Sessions: 1 session included in granule 3010 - Basic General Ledger</br></br>* Granule 410 - Additional BRL Business Essentials Users shows the number of user sessions purchased</br></br> * Total user sessions = number of granule 410 + 1 from granule 1200       |
| |BRL License -  Advanced Management| * Granule 1200 - NFR Sessions: Shows 1 session included in granule 3010 - Basic General Ledger </br></br>* Granule 420 - Additional BRL Advanced Management Users: Shows the number of user sessions purchased </br></br>* Total user sessions = number of granule 420 + 1 from granule 1200 |
| |MBLLicense       | * Granule 1200 - Additional Professional Users: Shows total user sessions. 1 session is included from granule 3010 - Basic General Ledger, the additional sessions are purchased sessions. Granule 1200 summarizes all sessions from granules 1,200, 1,210, 1,220, and 1,230. </br></br>* Total user sessions = number of granule 1200 </br></br>* **Note**: MBL Standard licenses also contain session information in granule 1,201. However, granule 1,201 does not include the user session that is included in the Basic General Ledger and therefore shows one session less than granule 1,200.        |
|Application Server sessions |         | * One Application Server session is included in granule 3010 - Basic General Ledger. However, this session does not show as an Application Server granule in the granule list in License Information.</br></br>* Granule 1415 – shows purchased application server sessions </br></br>* Total application server sessions = number of granule 1415 + 1 |

## Licensed Sessions in [!INCLUDE [nav_dev_short_md](includes/nav_dev_short_md.md)]

The **Licensed Sessions** field in the **Sessions** window in [!INCLUDE [nav_dev_short_md](includes/nav_dev_short_md.md)] shows how many total sessions, user sessions and application server sessions, you are licensed for.

To access **Licensed Sessions**, go to **File**, **Database**, **Information**, **Sessions** tab.

The **Licensed Sessions** field shows the total number of sessions included in a license, including both user and application server sessions. Therefore, you cannot use this field to determine the number of only user sessions or application server sessions.

## License Permissions Page

To create a page that lists all object permissions for a license, follow these steps:

1. In [!INCLUDE [nav_dev_short_md](includes/nav_dev_short_md.md)], go to **Tools**, **Object Designer**
2. Select **Page**, and then click **New**
3. Enter *Permission Range* or *2000000044* in the Table field
4. Select **Create a page using a wizard**
5. Select **List**
6. Click **OK**
7. Add all fields except **Index**
8. Select **Finish**
9. Save and close the page

This page will list all objects that the license currently uploaded to the database gives permissions for including what kind of permission (Read, Insert, Modify and Delete) and what type of permission (Direct(Yes) or Indirect).

## Protected Tables Report

Protected tables refer to those tables that can only be updated by objects with special permissions set. These tables are generally ledger tables, register tables, and certain history tables like posted document tables. The objects that have permission to update these tables (for example, posting routines and adjustment routines) can be created or modified only by customers who have a development license. Customer and partner development licenses give full read, insert, modify, and delete permissions for all base tables in the [!INCLUDE [navnow_md](includes/navnow_md.md)] database. Therefore, the report will not list any objects for these types of licenses.

To create a report listing all protected tables for a customer license, follow these steps:

1. In [!INCLUDE [nav_dev_short_md](includes/nav_dev_short_md.md)], go to **Tools**, **Object Designer**
2. Select **Report** and then click **New** 
3. Enter *Permission Range* or *2000000044* in the **Table** field 
4. Select **Create a report using a wizard** 
5. Select **Tabular-Type Report Wizard** 
6. Click **OK** 
7. Add all fields except **Index** 
8. Select **Finish** 
9. Go to **View**, **C/AL Code** or select F9 
10. In the `OnAfterGetRecord` trigger enter the following code:

    ```
    IF ("Insert Permission" <> "Insert Permission"::Indirect) AND
      ("Modify Permission" <> "Modify Permission"::Indirect) AND
      ("Delete Permission" <> "Delete Permission"::Indirect)
    THEN
      CurrReport.SKIP;
    ```

11. Save and close the report
12. To format the report correctly, design the report and go to **View**, **Sections** 
13. To create a RDLC layout, design the report and go to **Tools**, **Create Layout Suggestion**.


## See Also

[Session Timeout Settings and Configuration for Dynamics NAV](Understanding-Session-Timeouts.md)  
[Configuring [!INCLUDE [navnow_md](includes/navnow_md.md)]](Configuring-Microsoft-Dynamics-NAV.md)
[Deployment](Deployment.md)  

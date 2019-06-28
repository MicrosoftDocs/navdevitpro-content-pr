---
title: "Upgrading a Tenant"
ms.custom: na
ms.date: 12/28/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 014e3285-02be-459c-9a54-eae45ea71e04
author: jswymer
---

# Upgrading a Tenant
This article describes the process for upgrading tenants from one application version to another.

The upgrade process will not interrupt the service of existing tenants on the old application.

## Prerequisites
To complete this task, you deployment must meet these conditions:
-   Multitenant deployment environment that is using the shared schema data model.
-   There are no destructive changes between the old application version to the new application version. The new application can include new and modified objects (such as tables, pages, and codeunits), but any table changes are restricted to non-dectructive changes, like adding or renaming fields, or changing C/AL code.
-   The application includes required upgrade codeunits for ,

## Upgrade a Tenant
1.  Create a server instance for the new application version, and configure it for multinancy and shared schema data  model. Start the server instance.
2. Mount the new application database on the server instance.
3. Mount the tenant database that contains the tenant to the new server instance.

    ```
    Mount-NAVTenantDatabase "[Tenant Database ID]"
    ```

4. Synchronize the tenant database with the application database.

    ```
    Sync-NAVTenantDatabase "[Tenant Database ID]"
    ```

    Calling synchronize will alter or extend the SQL schema for the tenant database to match the application database. Tenant data is kept as it is. It registers into the shared tenant database that schema sync for v16 has completed. Tenants in the database are pending upgrade, and still not ready to be mounted. *

4. Mount the tenant that you want to upgrade to the new server instance.

    ```
    Mount-NAVTenant "[Tenant ID]"
    ```

5.  Run a data upgrade on the tenant.

    ```
    Start-NAVDataUpgrade "[Tenant ID]“ -SingleTransaction
    ```

    Starting the upgrade process will run the upgrade code units. When completed, the in-tenant state will be set to ”data upgraded to [application version].

Users of newly upgraded tenant are now acces the new application version through the new server instance.

Now, the tenant database is connected to both the old server instance and the new server instance. The older server instance and application version are still operable, and serving the other tenants.  You can upgrade the others tenants when appropriate by completing this smenant is served by NST 16, the rest by the old NST 15.

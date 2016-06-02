<properties
                pageTitle="Notifications | Project “Madeira”"
                description="Describes how you can develop notifications in the application using C/AL."
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# Upgrading to Project “Madeira”

This section describes how to upgrade to Project “Madeira” from the following Dynamics NAV versions:

-   Dynamics NAV 2013
-   Dynamics NAV 2013 R2
-   Dynamics NAV 2015
-   Dynamics NAV 2016

If you have an earlier version of Dynamics NAV, see [Upgrading versions earlier than Dynamics NAV 2013](#upgrading-versions-earlier-than-dynamics-nav-2013).

## How to upgrade to Project “Madeira”
The full upgrade process involves the following procedures:

-   Upgrading the application code.
-   Converting the database to the Project “Madeira” technical requirements (technical upgrade)
-   Upgrading the data

To complete the full upgrade process, follow these tasks in the specified order:

1.  [Upgrade the application code](upgrade-upgradingapplicationcode.md)
2.  [Upgrade the data](upgrade-upgradingdata.md)

    This task also covers converting the database to the Project “Madeira” technical requirements.

You can also decide only to convert the database to the Project “Madeira” technical requirements, and then upgrade the application and data later. For more information, see [Converting a Microsoft Dynamics NAV 2013 Database](upgrade-convertingdatabase.md).

### Additional information
Before you start, we recommend that you read the following information:

-   [Upgrade Considerations](upgrade-upgradeconsiderations.md)
-   [Automating the Upgrade Process using Sample Windows PowerShell Scripts](upgrade-automatingupgradeprocess.md)

## Upgrading versions earlier than Dynamics NAV 2013
If you have a version that is earlier than Dynamics NAV 2013, then before you upgrade to Project “Madeira”, you must upgrade to either Dynamics NAV 2013 or Dynamics NAV 2015 as outlined in the following table. Then you can use the automated upgrade process to upgrade to Project “Madeira”.

|  Version  |  Upgrade to  |
|-----------|--------------|
|Dynamics NAV 5.0|Dynamics NAV 2013|
|Dynamics NAV 4.0|Dynamics NAV 2013|
|Dynamics NAV 2009 R2|Dynamics NAV 2013 or Dynamics NAV 2015|
| Dynamics NAV 2009 SP1|Dynamics NAV 2013 or Dynamics NAV 2015|

For information about how to upgrade to Dynamics NAV 2013, see [Upgrading to Microsoft Dynamics NAV 2013](http://go.microsoft.com/fwlink/?LinkId=510382) in the MSDN Library.

For information about how to upgrade to Dynamics NAV 2015, see the [Dynamics NAV Team Blog](https://blogs.msdn.microsoft.com/nav/2014/11/09/cumulative-update-1-for-microsoft-dynamics-nav-2015-has-been-released/).

**Important:** If you upgrade from Microsoft Dynamics NAV 2009 R2 or earlier to Microsoft Dynamics NAV 2013 or later, the link between interaction records and logged email messages is lost. To resolve this issue, the administrator has to log all mails again to restore the links. For more information, see [Logging Interaction Links are Lost When You Upgrade from Microsoft Dynamics NAV 2009 R2](https://msdn.microsoft.com/library/hh167032(v=nav.90).

## See Also  
[Product and Architecture Overview](product-productarchitectureoverview.md)  
[Migrating to Multitenancy](deployment-migratingmultitenancy.md)  
[Deployment](deployment-overview.md)  
[Transforming Forms to Pages](http://go.microsoft.com/fwlink/?LinkId=510383)

---
title: New Zealand Features that are Moved, Removed, or Replaced | Microsoft Docs
description: We are constantly streamlining and adjusting our app in-step with market developments. Read about the features for New Zealand that we have moved, removed, or replaced.
author: bholtorf

ms.prod: dynamics-nav-2018
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: deprecated, New Zealand, local functionality
ms.date: 07/04/2018
ms.author: SorenGP

---

# Deprecated Features in the New Zealand Version of Microsoft Dynamics NAV 2018
This topic lists and describes the local functionality for New Zealand that has been removed from [!INCLUDE[navnow](includes/navnow_md.md)], made available from a new page or report, or replaced by a new feature.

## Business Activity Statements using ECI
A business activity statement (BAS) is a form that businesses must submit to the Australian Tax Office (ATO) on a monthly or quarterly basis. BAS reports both the total Goods and Services Tax (GST) collected from sales activities, which must be paid to the ATO, and the total GST paid on purchases, which is claimed as an input tax credit. For more information, see [Business Activity Statements](/dynamics-nav-app/localfunctionality/australia/business-activity-statements).

Companies can report their taxes manually using a form or electronically using Electronic Commerce Interface (ECI) software provided by the ATO.

|Moved, Removed, or Replaced?|Why?|
|----|----|
|Replaced|Electronic Commerce Interface (ECI) software is no longer being supported by the Australian Tax Office (ATO). Preparation of BAS using a template from ECI and export to an XML file for ECI software is no longer supported. You can use the GST Return report in the standard version to prepare information required to submit BAS to ATO. For more information, see [Report GST to the Tax Authorities](/business-central/finance-how-report-vat).|

## GST Sales and GST Purchase Reports
You can use the GST sales report and GST purchase report to reconcile the sales and purchase amounts recorded in business activity statements (BAS).

|Moved, Removed, or Replaced?|Why?|
|----|----|
|Replaced| To make the reports easier to use we have converted them to pages. For example, this means that you can filter by date, and export the data to Excel.  |

## Simulation Entries
The **Simulation Registers** window contains posted simulation entries that you can verify before transferring the simulation entries into real accounting entries.

|Moved, Removed, or Replaced?|Why?|
|----|----|
|Removed|The Simulation Entries feature has been replaced with the Posting Preview posting feature in the standard product.|

## See Also
[Upgrading to Microsoft Dynamics NAV 2018](upgrading-to-microsoft-dynamics-nav.md)  
[Upgrading the Application Code](upgrading-the-application-code.md)  
[Deprecated Fields, and Fields Marked as Obsolete](deprecated-fields.md)

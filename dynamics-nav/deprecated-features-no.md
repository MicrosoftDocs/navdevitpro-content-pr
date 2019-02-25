---
title: Norwegian Features that are Moved, Removed, or Replaced | Microsoft Docs
description: We are constantly streamlining and adjusting our app in-step with market developments. Read about the features for Norway that we have moved, removed, or replaced.
author: bholtorf

ms.prod: dynamics-nav-2018
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: deprecated, Norway, local functionality
ms.date: 08/29/2018
ms.author: bholtorf

---

# Deprecated Features in the Norwegian Version of Microsoft Dynamics NAV 2018
This topic lists and describes the local functionality for Norway that has been removed from [!INCLUDE[navnow](includes/navnow_md.md)], made available from a new page or report, or replaced by a new feature.

## Multiple Interest Rates
When you create finance charge terms and reminder terms, for delayed payment penalty, you can specify multiple interest rates so that the penalty fee is calculated from different interest rates in different periods.

|Moved, Removed, or Replaced?|Why?|
|----|----|
|Moved| The Multiple Interest Rates feature is no longer specific to Norway, so we have made it generally available in the standard product. |

## Paper Sources and Tray Numbers
When printing Norwegian sales documents, you can set up different tray numbers and paper sources on the first, last, and other pages.

|Moved, Removed, or Replaced?|Why?|
|----|----|
|Removed| The feature is not used. |  

## Objects or Fields Deleted in [!INCLUDE[nav2018](includes/nav2018_md.md)]
The following fields have been deleted as a result of features that have been removed.  

|Table ID|Table Name|Field ID|Field Name|
|--------|----------|--------|----------|
|81|Gen. Journal Line|10606|Source Curr. Inv.tax Amount|
|81|Gen. Journal Line|10607|Source Curr. Inv.tax Base|
|15000004|Waiting Journal|10606|Source Curr. Inv.tax Amount|
|15000004|Waiting Journal|10607|Source Curr. Inv.tax Base|
|49|Invoice Post. Buffer|10604|VAT Code|
|254|VAT Entry|10603|Add.-Curr. Inv.tax Amount|
|254|VAT Entry|10604|Add.-Curr. Inv.tax Base|
|78|Printer Selection|10600|First Page - Paper Source|
|78|Printer Selection|10601|First Page - Tray Number|
|78|Printer Selection|10602|Other Pages - Paper Source|
|78|Printer Selection|10603|Other Pages - Tray Number|
|78|Printer Selection|10604|Giro Page - Paper Source|
|78|Printer Selection|10605|Giro Page - Tray Number|
|311|Sales & Receivables Setup|10600|Print Receipt on Giro|

## See Also
[Upgrading to Microsoft Dynamics NAV 2018](upgrading-to-microsoft-dynamics-nav.md)  
[Upgrading the Application Code](upgrading-the-application-code.md)  
[Deprecated Fields, and Fields Marked as Obsolete](deprecated-fields.md)  
[Norway Local Functionality in [!INCLUDE[navnow](includes/navnow_md.md)]](/dynamics-nav-app/LocalFunctionality/Norway/norway-local-functionality)  

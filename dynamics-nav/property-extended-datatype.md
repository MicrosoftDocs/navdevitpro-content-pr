---
title: "ExtendedDataType Property | Dynamics NAV"
description: "Partial migration of topic for the ExtendedDataType property."
author: edupont04
ms.custom: na
ms.date: 04/06/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 0ff73303-b92d-4ce0-9a41-3952f8de7b7a
caps.latest.revision: 13
---

# ExtendedDataType Property
Sets the extended data type of a control.  

## Applies To  

-   Page Fields  

-   Table Fields  

## Remarks  
 The value of this property overrides the value of the table field and it converts a text field into one of the following:  

-   None  
-   Phone number  
-   Email address  
-   URL  
-   Filter (used on reports)  
-   Ratio (to monitor the progress bar)
-   Masked (displays the value as dots)
-   Person (displays a media field value as a round picture)

 This property affects the layout and behavior of controls on pages. For example, you can use it to add an icon next to an input field to indicate if the field specifies a phone number, email address, or URL. This property applies validation to the field.  

## See Also  
[Properties](Properties.md)  

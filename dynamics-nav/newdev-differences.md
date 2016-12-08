---
title: "Differences in the Dynamics NAV Development Environments"
description: "Describes the various differences between the old and the new development environment"
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/06/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: solsen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/newdev_dev_preview.md)]

# Differences in the Dynamics NAV Development Environments
Coming from the existing [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)], there are some differences and optimizations that you should familiarize yourself with. The following sections go through these changes.  

## Data types
|C/SIDE|New Development Environment|
|------|---------------------------|
|Dates are parsed based on culture settings.| Locale independent and supports only: ```ddmmyy``` and ```ddmmyyyy```|
|Boolean values could be expressed as **yes**/**no**| Boolean values are expressed as **true**/**false**.|
|Min, Max, and Init-Value decimal numbers without a fraction, for example ```5.0```, are implicitly converted to an integer in C/SIDE. Decimal numbers with fractions, for example, ```5.4``` compiled, but threw an error at runtime.|A decimal number is not accepted as an integer, for example ```5.0```, will give a compilation error.|

## Syntax updates
|C/SIDE|New Development Environment|
|------|---------------------------|
|The token for multilanguage comment is @@@|A multilanguage comment is marked with Comment|
||<!--Property values are considered syntax elements, thus they should obey the standard AL escaping rules.-->  |

Several properties have been renamed, to mention some:

|C/SIDE|New Development Environment|
|------|---------------------------|
|AutoFormatExpr|AutoFormatExpression|
|DataCaptionExpr|DataCaptionExpression|
|Layout|GridLayout|

## Naming
Controls, actions, and methods names must be unique on pages. In C/SIDE you could create a Part control with the same name as a method, which would give you a compilation error at runtime. This is now prevented, by disallowing duplicates. Likewise, actions and fields could have same names before, but that would have prevented page testability access, and will now throw a compilation error. <!-- check if this is correctly interpreted -->

## Property dependencies
Some properties require that you set another property. An example is ```PromotedCategory```, which requires that you have enabled the property ```Promoted```. The following table lists some of properties that have this dependency:

|Property|Depends on the property...|
|--------|-------------|
|PromotedCategory|Promoted|
|PromotedIsBig|Promoted|
|ValidateTableRelation|TableRelation|
|SourceTableTemporary|SourceTable|
|RunPageMode|RunObject| 

## See Also
[Getting Started](newdev-get-started.md)    
[Developer Reference](newdev-reference-overview.md)  
[Technical Reference for Dynamics NAV](technical-reference.md)

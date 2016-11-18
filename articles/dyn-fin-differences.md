---
title: "Differences from the Dynamics NAV Development Environment"
description: "Describes the various differences between the old and the new development environment"
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/18/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: solsen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/dyn_fin_dev_preview.md)]

# Differences from the Dynamics NAV Development Environment
Coming from the [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)], there are some differences and optimizations to be aware of. The following sections go through these changes.  

## Data types
|C/SIDE|New Development Environment|
|------|---------------------------|
|Dates are parsed based on culture settings.| Locale independent and supports only: ```ddMMyy``` and ```ddMMyyyy```|
|Boolean values could be expressed as **yes**/**no**| Boolean values are expressed as **true**/**false**.|
|Min, Max, and Init-Value decimal numbers without a fraction, for example ```5.0```, are implicitly converted to an integer in C/SIDE. Decimal numbers with fractions, for example, ```5.4``` compiled, but threw an error at runtime.|A decimal number is not accepted as an integer, for example ```5.0```, will give a compilation error.|

## Syntax
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
|||

## Properties
Some properties require that you set another property. An example is ```PromotedCategory```, which requires that you have enabled the property ```Promoted```.
The following table lists some of properties that have this dependency:

|Property|Depends on...|
|--------|-------------|
|PromotedCategory|Promoted|
|PromotedIsBig|Promoted|
|ValidateTableRelation|TableRelation|
|SourceTableTemporary|SourceTable|
|RunPageMode|RunObject| 

## Functions

## See Also
[Getting Started](dyn-fin-get-started.md)
<!--[Technical Reference for Dynamics NAV](technical-reference.md)-->

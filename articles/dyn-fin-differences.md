---
title: "Differences from the Dynamics NAV Development Environment"
description: "Describes the various differences between the old and the new development environment"
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/08/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: solsen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

# Differences from the Dynamics NAV Development Environment

## Data types
|C/SIDE|New Development Environment|
|------|---------------------------|
|Dates are parsed based on culture settings.| Locale independent and supports only: ```ddMMyy``` and ```ddMMyyyy```|
|Boolean values could be expressed as **yes**/**no**| Boolean values are expressed as **true**/**false**.|
|Min, Max, and Init-Value decimal numbers without a fraction, for example ```5.0```, are implicitly converted to an integer in C/SIDE. Decimal numbers with fractions, for example, ```5.4``` compiled, but threw an error at runtime.|A decimal number is not accepted as an integer, for example ```5.0```, will give a compilation error.|

## Syntax
|C/SIDE|New Development Environment|
|------|---------------------------|
|Token for multilanguage comment is @@@| Token for a multilanguage comment is Comment|

## Functions

## See Also

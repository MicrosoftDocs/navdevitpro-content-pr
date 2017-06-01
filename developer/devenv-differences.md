---
title: "Differences in the Development Environments"
description: "Describes the various differences between the old and the new development environment"
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/13/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: SusanneWindfeldPedersen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

# Differences in the Development Environments
Coming from the Dynamics NAV Development Environment and C/SIDE, there are some differences and optimizations that you should familiarize yourself with. The following sections go through these changes.  

## Data types
|C/SIDE|AL Development Environment|
|------|---------------------------|
|Dates are parsed based on culture settings.| Locale independent and supports only: ```yyyy-mm-ddD```.|
|Boolean values could be expressed as **yes**/**no**.| Boolean values are expressed as **true**/**false**.|

## Syntax updates
|C/SIDE|AL Development Environment|
|------|---------------------------|
|The token for multilanguage comment is @@@.|A multilanguage comment is marked with Comment.|

Several properties have been renamed, to mention some:

|C/SIDE|AL Development Environment|
|------|---------------------------|
|AutoFormatExpr|AutoFormatExpression|
|DataCaptionExpr|DataCaptionExpression|
|Layout|GridLayout|

## Pages
```Container``` and ```ContainerType``` elements in C/SIDE have been renamed to ```area(Content|FactBoxes|RoleCenter)``` and can be defined inside the ```layout``` section of the page.

The ```ActionContainer``` element in C/SIDE is renamed to ```area(Creation|Embedding|Navigation|Processing|Reporting|Sections)``` and can be defined inside the ```actions``` section of the page.

For syntax examples, see [Page Object](devenv-page-object.md).

## Naming
Controls, actions, and methods names must be unique on pages. In C/SIDE you could create a Part control with the same name as a method, which would give you an error at runtime. This is now prevented, by disallowing duplicates. Likewise, actions and fields could have same names before, but that would have prevented page testability access, and will now throw a compilation error.

## Property dependencies
Some properties require that you set another property. An example is ```PromotedCategory```, which requires that you have enabled the property ```Promoted```. The following table lists some of properties that have this dependency.

|Property|Depends on the property...|
|--------|-------------|
|PromotedCategory|Promoted|
|PromotedIsBig|Promoted|
|ValidateTableRelation|TableRelation|
|SourceTableTemporary|SourceTable|
|RunPageMode|RunObject|

## See Also
[Getting Started](devenv-get-started.md)    
[Developer Reference](devenv-reference-overview.md)  
[Technical Reference for Dynamics NAV](technical-reference.md)

---
title: "Differences in the Development Environments"
description: "Describes the various differences between the old and the new development environment"
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 09/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: solsen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Differences in the Development Environments
Coming from the Dynamics NAV Development Environment and C/SIDE, there are some differences and optimizations that you should familiarize yourself with. The following sections go through these changes.  

## Data types
|C/SIDE|AL Development Environment|
|------|---------------------------|
|Dates are parsed based on culture settings.| Locale independent and supports only: ```yyyy-mm-dd```.|
|Boolean values could be expressed as **yes**/**no**.| Boolean values are expressed as **true**/**false**.|
|For tables, integers could allow decimal values. For example, 5.0 converts to an integer value, 5.4 throws an error at runtime.| For tables, Min, Max, InitValue numbers with a fraction are expressed as `decimal`, thus they are not a valid integer type.|
|The largest constant integer could be `999999999999999`. | Transforms to `999'999'999'999'999.0`, a decimal value. In AL, this can be expressed as `999999999999999.0` or `999999999999999L`.|

## Syntax updates
|C/SIDE|AL Development Environment|
|------|---------------------------|
|The token for multilanguage comment is @@@.|A multilanguage comment is marked with Comment.|
|Supports TryFunction on code developed in C/SIDE.|Supports calling referenced TryFunctions from W1.|  

Several properties have been renamed, to mention some:

|C/SIDE|AL Development Environment|
|------|---------------------------|
|AutoFormatExpr|AutoFormatExpression|   
|DataCaptionExpr|DataCaptionExpression|
|Layout|GridLayout|

> !NOTE  
> Property values are considered as syntax elements; thus they should follow the standard AL escaping rules. 

## Pages

The ```ActionContainer``` elements in AL have been renamed; the following table lists the renamed elements:

|C/SIDE|AL Development Environment|
|------|---------------------------|
|ActionItems       | Processing    |
|ActivityButtons   | Sections      |
|HomeItems         | Embedding     |
|NewDocumentItems  | Creation      |
|RelatedInformation| Navigation    |
|Reports           | Reporting     |

For instance, ```area(Sections)``` can be defined inside the ```actions``` section of the page.

Likewise, ```Container``` and ```ContainerType``` elements in C/SIDE have been renamed to ```area(Content|FactBoxes|RoleCenter)``` and can be defined inside the ```layout``` section of the page.

For syntax examples, see [Page Object](devenv-page-object.md).

## Naming
Controls, actions, and methods names must be unique on pages. In C/SIDE, you could create a Part control with the same name as a method, which would give you an error at runtime. This is now prevented, by disallowing duplicates. Similarly, trigger and trigger event names are disallowed on matching application object types. Likewise, actions and fields could have same names before, but that would have prevented page testability access, and will now throw a compilation error. 


> !NOTE  
> Name on Controls and Actions on Pages is now mandatory. 

## Property dependencies
Some properties require that you set another property. An example is ```PromotedCategory```, which requires that you have enabled the property ```Promoted```. The following table lists some of the properties that have this dependency.

|Property|Depends on the property...|
|--------|-------------|
|PromotedCategory|Promoted|
|PromotedIsBig|Promoted|
|ValidateTableRelation|TableRelation|
|SourceTableTemporary|SourceTable|
|RunPageMode|RunObject|

## Limited functionality 

The ```InitValue``` property of type ```Duration``` is not allowed in new development environment.   
The ```InitValue``` of type ```DateTime``` only allows for the value ```0DT```.  

## See Also
[Developing Extensions](devenv-dev-overview.md)  
[Getting Started](devenv-get-started.md)    
[Developer Reference](devenv-reference-overview.md)  

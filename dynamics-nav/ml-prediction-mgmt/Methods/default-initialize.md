---
title: Default Initialize | Microsoft Docs
description: Initializes the codeunit with default values.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/02/2018
ms.author: bholtorf
---

# DefaultInitialize
Initializes the codeunit with default values:
 - resets the label field number to 0 (this is set when you call [SetLabel](set-label.md))
 - resets the last feature index to 0 (this is incremented each time you call [AddFeature](add-feature.md))
 - training set size to 80%

This method is called automatically when you call [Initialize](initialize.md).

<!--For more information, see [Essential AL Methods](../../devenv-essential-al-methods.md).-->

## Parameters
There are no parameters on this method.

## Return type
This method does not return any value.

## Example
The following exemple shows a typical use of default initialize, where you want to initialize the codeunit but you don't plan to make an actual call to the ML experiment, so you don't want to call [Initialize](initialize.md), which requires the API URI and key.
```
MLPredictionManagement.DefaultInitialize();

MLPredictionManagement.SetRecord(MyRecord);
MLPredictionManagement.AddFeature(MyRecord.FieldNo("My Feature Field Name"));
MLPredictionManagement.SetLabel(MyRecord.FieldNo("My Label Field Name"));    
if not MLPredictionManagement.IsDataSufficientForClassification() then
    exit;
```
<!--For more information, see [AL Data Types](../../devenv-al-data-types).-->

## See Also
[The ML Prediction Management API](../../ml-prediction-management-welcome.md)
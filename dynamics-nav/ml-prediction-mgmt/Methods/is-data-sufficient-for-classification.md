---
title: IS Data Sufficient for Classification | Microsoft Docs
description: Determines whether there is enough data to classify tags.
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

# IsDataSufficientForClassification
Checks if there is enough data in the previously set record, to train a classification model with enough confidence that the training will succeed. For this, we need the training set to contain every possible label.

<!--For more information, see [Essential AL Methods](../../devenv-essential-al-methods.md).-->

## Parameters
There are no parameters on this method.

## Return type
Boolean. True if the data is diverse enough, else false.

## Example
The following example initializes the codeunit, checks there is enough data to perform classification, then trains a new model with the data from the record that has been set on the codeunit.
```
MLPredictionManagement.Initialize(ApiUri, ApiKey, 0);
MLPredictionManagement.SetRecord(MyRecord);
MLPredictionManagement.AddFeature(MyRecord.FieldNo("My Feature Field Name"));
MLPredictionManagement.SetLabel(MyRecord.FieldNo("My Label Field Name"));

if MLPredictionManagement.IsDataSufficientForClassification() then
    MLPredictionManagement.Train(MyVarModelTxt, MyVarModelQuality);
```
<!--For more information, see [AL Data Types](../../devenv-al-data-types).-->

## See Also
[The ML Prediction Management API](../../ml-prediction-management-welcome.md)
---
title: Evaluate | Microsoft Docs
description: Evaluates the model to determine its quality.
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

# Evaluate
Evaluate a given model to determine its quality. The quality is the percentage of Labels predicted correclty on known data.

This function will throw an error if it is called but the codeunit has not been initialized before.

<!--For more information, see [Essential AL Methods](../../devenv-essential-al-methods.md).-->

## Parameters
|Parameter|Type|Description|
|---|---|---|
|Model|Text|The text represention of the model you want to evaluate. You get this text representation when calling [Train](train.md).|
|Quality|VAR Decimal|The result of the evaluation. It is in the range [0.0, 1.0]|


<!--For more information, see [Codeunit Properties](../../codeunit-properties.md).-->

## Return type
This method does not return any value. Its result is passed as a var parameter.

## Example
The following example initializes the codeunit, sets the record (table containing several lines where the label is known), then evaluate the model on this data and displays the quality.
```
MLPredictionManagement.Initialize(ApiUri, ApiKey, 0);
MLPredictionManagement.SetRecord(MyRecord);
MLPredictionManagement.AddFeature(MyRecord.FieldNo("My Feature Field Name"));
MLPredictionManagement.SetLabel(MyRecord.FieldNo("My Label Field Name"));

MLPredictionManagement.Evaluate(MyModelTxt, ModelQuality);
Message('Model quality is %1', ModelQuality);
```
<!--For more information, see [AL Data Types](../../devenv-al-data-types).-->

## See Also
[The ML Prediction Management API](../../ml-prediction-management-welcome.md)
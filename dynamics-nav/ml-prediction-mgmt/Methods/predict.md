---
title: Predict | Microsoft Docs
description: Generates a prediction.
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

# Predict
Predicts the value of the label using a given model and record.
The label field will be directly set to the prediction value in everty line of the record variable.

<!--For more information, see [Essential AL Methods](../../devenv-essential-al-methods.md).-->

## Parameters
|Parameter|Type|Description|
|---|---|---|
|Model|Text|The text represention of the model you want to evaluate. You get this text representation when calling [Train](train.md).|


<!--For more information, see [Codeunit Properties](../../codeunit-properties.md).-->

## Return type
This method does not return any value. The prediction values are set directly in the record passed to the codeunit when calling [SetRecord](set-record.md) prior to calling Predict.

## Example
The following example initializes the codeunit, sets the record and calls predict. Then it displays the value predicted on the first line of the record.
```
MLPredictionManagement.Initialize(ApiUri, ApiKey, 0);
MLPredictionManagement.SetRecord(MyRecord);
MLPredictionManagement.AddFeature(MyRecord.FieldNo("My Feature Field Name"));
MLPredictionManagement.SetLabel(MyRecord.FieldNo("My Label Field Name"));

MLPredictionManagement.Predict(MyModelTxt);

MyRecord.FindFirst();
Message('Label was predicted to %1 on the first line.', MyRecord."My Label Field Name");
```
<!--For more information, see [AL Data Types](../../devenv-al-data-types).-->

## See Also
[The ML Prediction Management API](../../ml-prediction-management-welcome.md)
---
title: Add a Feature | Microsoft Docs
description: Defines that a field of the record is a feature.
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

# AddFeature
Indicates that a field of the previously set record on the codeunit (see [SetRecord](set-record.md)) is a feature.

You will get an error if:
- the field number does not exist on the set record
- you define more than 25 features
- you define a feature on the same field as the label
- you add the same feature field number twice

<!--For more information, see [Essential AL Methods](../../devenv-essential-al-methods.md).-->

## Parameters
|Parameter|Type|Description|
|---|---|---|
|FeatureFieldNo|Integer|The field number of a feature.|


<!--For more information, see [Codeunit Properties](../../codeunit-properties.md).-->

## Return type
This method does not return any value.

## Example
The following exampleinitializes the codeunit, sets the record, then adds one feature, defines the label and calls Predict.
```
MLPredictionManagement.Initialize(ApiUri, ApiKey, 0);
MLPredictionManagement.SetRecord(MyRecord);

MLPredictionManagement.AddFeature(MyRecord.FieldNo("My Feature Field Name"));

MLPredictionManagement.SetLabel(MyRecord.FieldNo("My Label Field Name"));
MLPredictionManagement.Predict(MyModelTxt);
```
<!--For more information, see [AL Data Types](../../devenv-al-data-types).-->

## See Also
[The ML Prediction Management API](../../ml-prediction-management-welcome.md)
---
title: Set Record | Microsoft Docs
description: Set the record on codeunit 2003.
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

# SetRecord
Sets the record to be used by the next calls to codeunit 2003 methods.
This includes methods:
- [AddFeature](add-feature.md)
- [SetLabel](set-label.md)
- [Train](train.md)
- [Predict](predict.md)
- [Evaluate](evaluate.md)
- [IsDataSufficientForClassification](is-data-sufficient-for-classification.md)

<!--For more information, see [Essential AL Methods](../../devenv-essential-al-methods.md).-->

## Parameters
|Parameter|Type|Description|
|---|---|---|
|RecordVariant|Variant|The record to use for next calls to the codeunit. |

<!--For more information, see [Codeunit Properties](../../codeunit-properties.md).-->

## Return type
This method does not return any value.

## Example
The following example populates a record with one line to predict on, then calls predict.
```
MLPredictionManagement.Initialize(ApiUri, ApiKey, 0);

MyRecord.DeleteAll();
MyRecord.Init();
MyRecord.Validate("My Feature Field Name", 42);
MyRecord.Insert();
MLPredictionManagement.SetRecord(MyRecord);

MLPredictionManagement.AddFeature(MyRecord.FieldNo("My Feature Field Name"));
MLPredictionManagement.SetLabel(MyRecord.FieldNo("My Label Field Name"));
MLPredictionManagement.Predict(MyModelTxt);
```
<!--For more information, see [AL Data Types](../../devenv-al-data-types).-->

## See Also
[The ML Prediction Management API](../../ml-prediction-management-welcome.md)
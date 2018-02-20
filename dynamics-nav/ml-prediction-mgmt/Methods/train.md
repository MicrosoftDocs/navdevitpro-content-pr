---
title: Train | Microsoft Docs
description: Train the predictive model on the data you provide.
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

# Train
Trains a model based on data contained in the record previously set on the codeunit when calling [SetRecord](set-record.md).

<!--For more information, see [Essential AL Methods](../../devenv-essential-al-methods.md).-->

## Parameters
|Parameter|Type|Description|
|---|---|---|
|Model|VAR Text|The model representation as text. This is a long string and it should be stored in a BLOB field.|
|Quality|VAR Decimal|The model quality, between 0 and 1.|

<!--For more information, see [Codeunit Properties](../../codeunit-properties.md).-->

## Return type
This method does not return any value. The result of the training is set in the VAR parameters passed to the method.

## Example
The following example initializes the codeunit, sets the record containing the data for the training, checks if there is enough data for training a classification model, then trains the model. After checking the quality is good enough, it saves the model in a BLOB field.
```
MLPredictionManagement.Initialize(ApiUri, ApiKey, 0);
MLPredictionManagement.SetRecord(MyRecord);
MLPredictionManagement.AddFeature(MyRecord.FieldNo("My Feature Field Name"));
MLPredictionManagement.SetLabel(MyRecord.FieldNo("My Label Field Name"));

if not MLPredictionManagement.IsDataSufficientForClassification() then
    exit;

MLPredictionManagement.Train(MyVarModelTxt, MyVarModelQuality);

if MyVarModelQuality > 0.8 then begin
    RecordRef.GetTable(MyModelStorageTable);
    TypeHelper.SetBlobString(RecordRef, MyModelStorageTable.FieldNo("My Model Blob"), ModelAsText);
end;
```

<!--For more information, see [AL Data Types](../../devenv-al-data-types).-->

## See Also
[The ML Prediction Management API](../../ml-prediction-management-welcome.md)
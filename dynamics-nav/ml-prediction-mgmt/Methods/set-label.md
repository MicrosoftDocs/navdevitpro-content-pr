---
title: Set Label | Microsoft Docs
description: Defines which field of the record is the label.
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

# SetLabel
Defines which field of the record previously set on the codeunit (see [SetRecord](set-record.md)) is the label (the field to predict).

You will get an error if:
- the field number does not exist on the set record

<!--For more information, see [Essential AL Methods](../../devenv-essential-al-methods.md).-->

## Parameters
|Parameter|Type|Description|
|---|---|---|
|LabelFieldNo|Integer|The field ID of the label|

<!--For more information, see [Codeunit Properties](../../codeunit-properties.md).-->

## Return type
This method does not return any value.

## Example
<!--ADD CODE EXAMPLE BETWEEN THE BACKTICKS-->
The following example Initializes the codeunit, then sets the record to use, add one feature and the label, then calls predict.

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
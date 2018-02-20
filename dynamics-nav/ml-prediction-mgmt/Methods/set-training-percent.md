---
title: Set Training Percent | Microsoft Docs
description: Sets the training set size as a percentage of the total dataset size.
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

# SetTrainingPercent
Get the training set size as a percentage of the total dataset size.

This function will throw an error if the percentage value you are trying to set is outside of the ]0.0, 1.0[ range.

<!--For more information, see [Essential AL Methods](../../devenv-essential-al-methods.md).-->

## Parameters
|Parameter|Type|Description|
|---|---|---|
|TrainingPercentValue|Decimal|The percentage of data to take in the data set to perform the training. The remaining will be used as validation data for the model.|

## Return type
This method does not return any value.

## Example
The following exemple sets the training percentage to 50%, then calls Initialize, then sets it again to 50% after the training percentage has been automatically set to the default of 80% when calling Initialize.
```
MLPredictionManagement.SetTrainingPercent(0.5);
MLPredictionManagement.Initialize(ApiUri, ApiKey, 0);

if MLPredictionManagement.GetTrainingPercent() <> 0.8 then begin
    Message('Initialize called SefaultInitialize and set the training percentage to 80%. Changing it back to 50%!');
    MLPredictionManagement.SetTrainingPercent(0.5);
end;
```

<!--For more information, see [AL Data Types](../../devenv-al-data-types).-->

## See Also
[The ML Prediction Management API](../../ml-prediction-management-welcome.md)
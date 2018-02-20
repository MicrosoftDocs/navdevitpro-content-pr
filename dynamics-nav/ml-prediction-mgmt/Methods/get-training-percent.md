---
title: Get Training Percent | Microsoft Docs
description: Gets the training set size as a percentage of the total dataset size.
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

# GetTrainingPercent
Get the training set size as a percentage (as a decimal value) of the total dataset size (the dataset is contained in the previously set record with [SetRecord](set-record.md)).

For more information, see [Essential AL Methods](../../devenv-essential-al-methods.md).

## Parameters
There are no parameters on this method.

## Return type
Decimal. The value is in the ]0.0, 1.0[ range.

## Example
The following exemple sets the training percentage to 50%, then calls Initialize, then checks the training percentage has been automatically set to the default of 80% when calling Initialize.
```
MLPredictionManagement.SetTrainingPercent(0.5);
MLPredictionManagement.Initialize(ApiUri, ApiKey, 0);

if MLPredictionManagement.GetTrainingPercent() <> 0.8 then
    Message('Expected Initialize to call SefaultInitialize and set the training percentage to 80%.')
```

<!--For more information, see [AL Data Types](../../devenv-al-data-types).-->

## See Also
[The ML Prediction Management API](../../ml-prediction-management-welcome.md)
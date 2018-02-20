---
title: Initialize | Microsoft Docs
description: Initializes codeunit 2003.
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

# Initialize
Initializes codeunit 2003 with the ML Experiment API URI, API Key and timeout.

<!--For more information, see [Essential AL Methods](../../devenv-essential-al-methods.md).-->

## Parameters
|Parameter|Type|Description|
|---|---|---|
|ApiKey|Text|API Key needed to access your ML Experiment.|
|ApiUri|Text|API URI to your ML Experiment.|
|Timeout|Integer|Timeout value, in seconds, that will be used when contacting the ML Experiment web service. 0 will keep the default timeout of 100s.|

<!--For more information, see [Codeunit Properties](../../codeunit-properties.md).-->

## Return type
This method does not return any value.

## Example
The following exemple initializes the codeunit with the API URI, API Key and the default timeout, then calls predict on some record.
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
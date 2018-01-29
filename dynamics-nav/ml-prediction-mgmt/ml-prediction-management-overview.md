---
title: Using ML Prediction Management | Microsoft Docs
description: Provides an overview of the methods in codeunit 2003 to use in each phase of implementing a predictive model.
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

# Working with ML Prediction Management
This topic describes the methods to use to prepare data for analysis, train the model on data and evaluate its quality, and make a prediction that is accompanied by a confidence score that indicates how accurate the prediction is. All of these methods are available in codeunit 2003.

For more information about codeunits, see [Dynamics NAV Codeunits Overview](https://docs.microsoft.com/en-us/dynamics-nav/codeunits).

## How to initialize the codeunit
The methods in the following table initialize codeunit 2003.

|Method|Description|
|---|---|
|[Default Initialize](default-initialize.md)|<short description, starts with a verb>|
|[Initialize](initialize.md)|<short description, starts with a verb>|

## How to prepare your data
The methods in the following table prepare data.

|Method|Description|
|---|---|
|[setRecord](set-record.md)|<short description, starts with a verb>|
|[addFeature](add-feature.md)|<short description, starts with a verb>|
|[setLabel](set-label.md)|<short description, starts with a verb>|
|[setTrainingPercent](set-training-percent.md)|<short description, starts with a verb>|
|[isDataSufficientForClassification](is-data-sufficient-for-classification.md)|<short description, starts with a verb>|

## How to create a working model 
The methods in the following table create a model that can generate predictions.

|Method|Description|
|---|---|
|[train](train.md)|<short description, starts with a verb>|
|[evaluate](evaluate.md)|<short description, starts with a verb>|
|[predict](predict.md)|<short description, starts with a verb>|

## See Also
[Welcome to ML Prediction Management](../ml-prediction-management-welcome.md)
[Getting Started with ML Prediction Management](../ml-prediction-management-get-started.md)
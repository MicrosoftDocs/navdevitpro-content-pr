---
title: Using ML Prediction Management API | Microsoft Docs
description: Provides an overview of the methods in each phase.
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

# Working with the ML Prediction Management API
This topic describes the methods to use to prepare data for analysis, train the model on data and evaluate its quality, and make a prediction that is accompanied by a confidence score that indicates how accurate the prediction is. All of these methods are available in codeunit 2003.

## How to initialize the codeunit
The methods in the following table initialize codeunit 2003.

|Method|Description|
|---|---|
|[DefaultInitialize](Methods/default-initialize.md)|Initializes the codeunit with default values|
|[Initialize](Methods/initialize.md)|Initialize the codeunit, providing your values.|

Before using the codeunit, you need to initialize it, by calling the Initialize method, providing your API URI, API Key, and timeout. 

## Prepare your data
The methods in the following table prepare data.

|Method|Description|
|---|---|
|[SetRecord](Methods/set-record.md)|<short description, starts with a verb>|
|[AddFeature](Methods/add-feature.md)|<short description, starts with a verb>|
|[SetLabel](Methods/set-label.md)|<short description, starts with a verb>|
|[SetTrainingPercent](Methods/set-training-percent.md)|<short description, starts with a verb>|
|[GetTrainingPercent](Methods/get-training-percent.md)|<short description, starts with a verb>|
|[IsDataSufficientForClassification](Methods/is-data-sufficient-for-classification.md)|<short description, starts with a verb>|

## Create a Working Model 
The methods in the following table create a model that can generate predictions.

|Method|Description|
|---|---|
|[train](Methods/train.md)|<short description, starts with a verb>|
|[evaluate](Methods/evaluate.md)|<short description, starts with a verb>|
|[predict](Methods/predict.md)|<short description, starts with a verb>|

## See Also
Getting Started with the ML Prediction Management API
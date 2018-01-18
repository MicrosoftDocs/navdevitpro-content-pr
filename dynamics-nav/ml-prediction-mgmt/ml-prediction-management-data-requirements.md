---
title: Amounts and Variance in Data | Microsoft Docs
description: Read about the data requirements for making accurate predictions.
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

## Data Requirements for the ML Prediction Management API
<!--Might be better to have this in the Getting Started topic.-->

The more data you have about payments that were on-time and late, the better. As a general rule of thumb, you should have two or three hundred records of each type, that is, both late payments and payments that were on-time. However, depending on other factors, such as variance in your data, you might be able to get accurate predictions even if you have less than that. For example, you might try actually removing some of your data and then retraining your model, or just train the model several times. Our API will check the quality of your model, which you can use to decide whether the predictions are reliable enough to use. 
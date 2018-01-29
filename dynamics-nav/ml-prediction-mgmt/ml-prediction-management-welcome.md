---
title: Introduction to ML Prediction Management API | Microsoft Docs
description: Learn about building your own predictive model and integrating it with [!INCLUDE[d365fin_long](../includes/d365fin_long_md.md)].
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

# Integrate With Cortana Intelligence
Learn how to build a predictive model based on our experiments in Azure Machine Learning Studio, deploy the model as a web service, and then integrate the model with [!INCLUDE[d365fin_long](../includes/d365fin_long_md.md)].

The quality and accuracy of the algorithms used in artificial intelligence (AI) and Azure machine learning (ML) are improving by leaps and bounds, and we see lots of ways to use them in [!INCLUDE[d365fin_long](../includes/d365fin_long_md.md)]. The following extensions are examples of the features we already offer that use Azure services:
  
* **Sales and Inventory Forecasts** and **Cash Flow Forecasts** use a Time Series experiment to help you manage the movement of inventory and cash through your business. For more information, see [Sales and Inventory Forecasts](https://docs.microsoft.com/en-us/dynamics365/financials/ui-extensions-sales-forecast) and [Set Up Cash Flow Forecasts](https://docs.microsoft.com/en-us/dynamics365/financials/finance-setup-cash-flow-analyses).
* **Image Analyzer** uses the [Computer Vision API](https://azure.microsoft.com/en-us/services/cognitive-services/computer-vision/) from Azure Cognitive Services to detect attributes in images attached to items and contact persons. For more information, see [The Image Analyzer Extension](https://docs.microsoft.com/en-us/dynamics365/financials/ui-extensions-image-analyzer).
* **Late Payment Predictions** help you manage receivables by predicting whether invoices will be paid on-time. For more information, see [The Late Payment Predictions](ui-extensions-late-payment-prediction.md).

We want to encourage and support you in building your own extensions. To make it easier for you to get started we have created a few experiments in Azure Machine Learning Studio. You can use the experiments to create and train your own predictive model, and then deploy it as a web service that can integrate with [!INCLUDE[d365fin_long](../includes/d365fin_long_md.md)]. We have also created a few codeunits that are useful in this process. For more information, see [Getting Started with ML Prediction Management](ml-prediction-management-get-started.md).

## Food for Thought
An enterprise resource planning solution like [!INCLUDE[d365fin](../includes/d365fin_md.md)] contains plenty of opportunities to benefit from getting a peek into the future. Here are just a few predictions you might consider implementing:

* When an expected item receipt will be overdue.
* Whether a sales campaign will increase sales.
* Whether a resource will complete job on time.

## See Also
[Getting Started with ML Prediction Management](ml-prediction-management-get-started.md)
[Working with ML Prediction Management API]




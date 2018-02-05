---
title: Getting Started with ML Prediction Management API | Microsoft Docs
description: Read about the steps to get going with a predictive model.
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
# Getting Started
We want to encourage and support you in building your own extensions. To make it easier to get started we have created a few experiments in Azure Machine Learning Studio. You can use the experiments to create and train your own predictive model, and then deploy it as a web service that can integrate with [!INCLUDE[d365fin_long](../includes/d365fin_long_md.md)]. We have also created a few codeunits that are useful in this process. For more information, see [Getting Started with ML Prediction Management](ml-prediction-management-get-started.md). This topic describes the requirements for extending [!INCLUDE[d365fin_long](../includes/d365fin_long_md.md)] to use an Azure service.

### Food for Thought
An enterprise resource planning solution like [!INCLUDE[d365fin](../includes/d365fin_md.md)] contains plenty of opportunities to benefit from getting a peek into the future. Here are just a few predictions you might consider implementing:

* When an expected item receipt will be overdue.
* Whether a sales campaign will increase sales.
* Whether a resource will complete job on time.

## Microsoft Azure Machine Learning Studio
You will use Azure Machine Learning Studio, so one of the first things you need to do is get a subscription to Azure. In short, Machine Learning Studio combines data science, predictive analytics, cloud resources, and your data to help you build, test, and deploy predictive models as web services that you can integrate with other apps. You can also save them to Azure, and share (or sell) them.

Getting started ot just experimenting with Studio is easy. Go to the [Microsoft Azure](https://azure.microsoft.com/en-gb/trial/get-started-machine-learning/) website and sign up for an account. If you just want to try it out, you can choose the free (green) model. The model is based in the South Central United States and has limited scalability, but it’s fine for experimenting. Studio contains sample models, data, algorithms, data manipulation and transformation modules, R and Python runtime, and much more.
 
## About the Tools We Provide
The tools we provide give developers access to advanced algorithms that process data to make predictions about the future state of one or more aspects of your business. For example, our Late Payment Prediction extension uses it to predict whether a customer will pay an invoice on-time. The components of the framework include two experiments in the Cortana Intelligence Gallery, and two codeunits in the developer environment.

### About Our Experiments
Our ML experts have created two experiments that you can use to create your own model, or you can copy our model and modify it to suit your needs. Our model uses the Execute R Script module to run the R scripts that calculate forecasts and determine their accuracy.

The experiments are available in the [Cortana Intelligence Gallery](https://go.microsoft.com/fwlink/?linkid=828352):

* Forecasting Model for [!INCLUDE[d365fin_long](../includes/d365fin_long_md.md)]  
* Late Payment Prediction Model for [!INCLUDE[d365fin_long](../includes/d365fin_long_md.md)]

### About the Codeunits We Provide
You can use the following codeunits when you build your own extension:

* Codeunit 2003 for predictions  
* Codeunit 2000 for time series management  <!--Need the codeunit number. Also, is this codeunit used for both sales and inventory forecasts and cash flow forecasts?-->

## Predictive Models
ML Prediction Management uses a classification model. The goal of a classification model is to assign something to a predefined class, or category. These classes or categories are called "labels," and are defined when you train the model. For this API, we have two labels, **Late** and **On-Time.**

## Data Requirements
The more data you have, the better. For example, the dataset we use to train the model for ML Prediction management needed two or three hundred records of both late and on-time payments. However, other factors such as variance also influence the accuracy of predictions. When you are determining whether you have enough data, for example, you might try removing some of your data and then retraining your model, or just train the model several times. Our models contain a check that examines the quality of a model. If you copy our model, you can decide whether the predictions are reliable enough to use. 

##See Also
[Welcome to the ML Prediction Management Documentation](ml-prediction-management-welcome.md)
[ML Prediction Management Overview](ml-prediction-management-overview.md)
[Working with ML Prediction Management]
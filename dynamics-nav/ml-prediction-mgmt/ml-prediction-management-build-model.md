---
title: Build and Test a Predictive Model | Microsoft Docs
description: Learn how to build and test a predictive model in Azure Machine Learning Studio.
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
# How to: Build and Test Your Own Predictive Model
You can use Azure Machine Learning Studio to build your own predictive model and deploy it as a web service that you can integrate with [!INCLUDE[d365fin](../includes/d365fin_md.md)]. To use your own model, you must subscribe to Azure Machine Learning. For more information, see [Azure Machine Learning Studio Documentation](https://go.microsoft.com/fwlink/?linkid=861765).  

## Building a Model Based on Our Experiment
You can share your data with our predictive experiment in Azure Machine Learning, and let our experiment create and train a predictive model based on your data.  







  
> [!Note]
> The quality of the model is important. When our predictive experiment uses your data to train a model it determines a quality value for the model as a percentage. The model quality indicates how accurate the model's predictions are likely to be. Several factors can impact the quality of a model. For example, these factors might be that there simply was not enough data, or the data did not contain enough variation. You can view the quality of the model you are currently using. You can also specify a minimum threshold for the model quality. Models with a quality value below the threshold will not produce predictions.  
  
If you create your own model in Azure Machine Learning Studio, without using the tools in [!INCLUDE[d365fin](../includes/d365fin_md.md)], you must provide your credentials so that [!INCLUDE[d365fin](../includes/d365fin_md.md)] can access the model. There are a couple of steps to do that:



1. Choose the ![Search for Page or Report](../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Late Payment Prediction Setup**, and then choose the related link.  
2. Choose the **Use My Model** check box.  
3. In the **Selected Model** field, choose **My Model**.  
4. On the **My Model Credentials** FastTab, enter the API URL and API Key for your model.  



##See Also  
[Azure Machine Learning Studio Documentation](https://docs.microsoft.com/en-us/azure/machine-learning/studio/)  
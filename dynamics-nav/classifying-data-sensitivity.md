---
title: "Classifying Data Sensitivity"
ms.author: bholtorf
ms.custom: na
ms.date: 02/12/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
author: bholtorf
---

# Classifying Data Sensitivity
To classify the fields that hold sensitive or personal data, a Microsoft partner can set the Data Classification property on fields and tables. This requires access to the database tables, either through the development environment or by running a Windows PowerShell script.  

As a customer, you can add a second level of classification by specifying sensitivity levels for the data you store in standard and custom fields. For example, this is particularly useful if you have repurposed a standard field, or added a new field on a page. The following table describes data sensitivity levels.

|Sensitivity|Description|
|----|----|
|Sensitive | Information about a data subject's racial or ethnic origin, political opinions, religious beliefs, involvement with trade unions, physical or mental health, sexuality, or details about criminal offenses. |
|Personal | Information that can be used to identify a data subject, either directly or in combination with other data or information.|
|Confidential | Business data that you use for accounting or other business purposes, and do not want to expose to other entities. For example, this might include ledger entries.|
|Normal | General data that does not belong to any other categories.|

## See Also
[Classifying Data](classifying-data.md)

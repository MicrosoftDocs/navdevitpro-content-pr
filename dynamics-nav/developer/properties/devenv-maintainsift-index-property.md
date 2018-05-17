---
title: "MaintainSIFTIndex Property"
ms.custom: na
ms.date: 06/16/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 4bfc7edc-4561-4da4-b725-623d1c86be99
caps.latest.revision: 7
author: SusanneWindfeldPedersen
redirect_url: /dynamics365/business-central/dev-itpro/developer/properties/devenv-properties
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# MaintainSIFTIndex Property
Sets the value to determine whether SIFT structures should be created in SQL Server to support the corresponding SumIndexFields for the [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] key.  
  
## Applies To  
 Keys  
  
## Property Value  
 **True** to create the SIFT structures in SQL Server; otherwise, **false**. The default is **true**.  
  
## Remarks  
 SumIndexFields are created in [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] to support FlowField calculations and other fast summing operations. SQL Server can sum numeric data by scanning the table. If the SIFT structures exist for the SumIndexFields, summing the fields is faster, especially for large sets of records, but modifications to the table are slower because the SIFT structures must also be maintained.  
  
 In situations where SumIndexFields must be created on a key to enable FlowField calculations, but the calculations are performed infrequently or on small sets of data, you can disable this property to prevent slow modifications to the table.  
  
## See Also  
 [Properties](devenv-properties.md)
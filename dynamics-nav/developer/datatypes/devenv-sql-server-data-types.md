---
title: "SQL Server Data Types"
ms.custom: na
ms.date: 06/08/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 86815380-0d8c-4cf2-aabf-1ab22cb51308
caps.latest.revision: 10
author: SusanneWindfeldPedersen
redirect_url: /dynamics365/business-central/dev-itpro/developer/datatypes/devenv-al-data-types
---
# SQL Server Data Types
Every available [!INCLUDE[d365fin_md](../includes/d365fin_md.md)] data type is mapped to an appropriate SQL Server data type. The following table shows which SQL Server data type is used for the corresponding Microsoft Dynamics NAV data type.  
  
|Microsoft Dynamics NAV Data Type|SQL Server Data Type|  
|--------------------------------------|--------------------------|  
|BigInteger|BIGINT|  
|BLOB|IMAGE|  
|Boolean|TINYINT|  
|Code(n)|NVARCHAR(n), INTEGER, SQL_VARIANT|  
|Date|DATETIME|  
|DateFormula|VARCHAR(32)|  
|Decimal|DECIMAL(38,20)|  
|Duration|BIGINT|  
|GUID|UNIQUEIDENTIFIER|  
|Integer|INTEGER|  
|Option|INTEGER|  
|RecordID|VARBINARY(n)|  
|TableFilter|VARBINARY(252)|  
|Text(n)|NVARCHAR(n)|  
|Time|DATETIME|  
  
 Each of the SQL Server data types is created as NOT NULL except the IMAGE type, which allows NULL.

## See Also
[AL Data Types](devenv-al-data-types.md)  
---
title: "TestTableRelation Property"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: d4b37c19-bcb3-49d2-868d-126be1d383be
caps.latest.revision: 8
author: SusanneWindfeldPedersen
redirect_url: /dynamics365/business-central/dev-itpro/developer/properties/devenv-properties
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# TestTableRelation Property
Sets whether to include this field when evaluating field relations between primary and secondary indexes.  
  
## Applies To  
 Fields  
  
## Property Value  
 **True** if you want to test the table relationship for this field; otherwise, **false**. The default is **true**.  
  
## Remarks  
 You may want to use this property to exclude certain fields from the table relation test. For example, if a table in your application has a field that is a foreign key, but records from the other table may have been deleted, then you would not want to test the relationship with this table. Only set this property to **false** if you are certain that testing this relationship would only cause errors that do not compromise the consistency of your application tables.  
  
 This test is available from the **Database** option on the **File** menu. You can use this property to limit the number of relationships that are tested.  
  
 If you set the ValidateTableRelation property to **false**, then you should also set the TestTableRelation property to **false**. Otherwise, a database test on the field relations in a database may fail.  
  
## See Also  
 [TestTableRelation](devenv-testtablerelation-property.md)   
 [ValidateTableRelation Property](devenv-validatetablerelation-property.md)
---
title: "Method Attributes"
ms.custom: na
ms.date: 06/07/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-financials"
author: jswymer
---
# Method Attributes
An attribute is modifiers on method declarations that specifies information about that controls the methods use and behavior. For example, decorating a method with Integration attributes specifes the method to be an event publisher. An attribute can have one or more arguments that set properties for the instance of the method. Attributes are placed before the method, and have the following syntax:

```
[Attribute_Name(ArgumentName : data_type, ArgumentName : data_type)]
```

For example, the Integration attribute has two arguments, and the syntax is:

```  
[Integration(IncludeSender : Boolean, GlobalVarAccess : Boolean)] 
```    
  

## Attributes  
The following method attributes are available:

[Integration Attribute](devenv-integration-attribute.md)   
[Business Attribute](devenv-business-attribute.md)  
[UpgradePerCompany](devenv-upgradepercompany-attribute.md)  
[UpgradePerDatabase](devenv-upgradeperdatabase-attribute.md) 

## See Also  
[AL Data Types](devenv-al-data-types.md)  
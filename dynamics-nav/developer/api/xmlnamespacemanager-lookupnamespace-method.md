---
title: "LookupNamespace Method"
ms.author: solsen
ms.custom: na
ms.date: 12/27/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 620f0e32-eadc-43e9-8f6e-8fc0b12c3aaf
caps.latest.revision: 1
manager: edupont
author: SusanneWindfeldPedersen
redirect_url: /dynamics365/business-central/dev-itpro/developer/devenv-restapi-overview
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# LookupNamespace Method
Gets the namespace URI for the specified prefix.  
```  
[Ok := ] XmlNamespaceManager.LookupNamespace(Prefix, Result)  
```  
## Parameters
*Prefix*    
&emsp;Type: [String](../datatypes/devenv-text-data-type.md)  
The prefix whose namespace URI you want to resolve. To match the default namespace, pass an empty string.  
  
*Result*    
&emsp;Type: [Text](../datatypes/devenv-text-data-type.md)  
The namespace URI for prefix.  
  
## Return Value
*Ok*  
&emsp;Type: [Boolean](../datatypes/devenv-boolean-data-type.md)  
**True** if the operation was successful; otherwise, **false**.  
If you omit this optional return value and the operation does not execute successfully, a run-time error will occur.  
  
## See Also
[XmlNamespaceManager](xmlnamespacemanager-class.md)  
[HTTP, JSON, TextBuilder, and XML API](../devenv-restapi-overview.md)  
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

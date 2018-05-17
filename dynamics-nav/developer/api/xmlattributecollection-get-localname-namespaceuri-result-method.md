---
title: "Get Method"
ms.author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/20/2017
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

# Get Method
Gets the specified attribute.  
```  
[Ok := ] XmlAttributeCollection.Get(LocalName, NamespaceUri, Result)  
```  
## Parameters
*LocalName*    
&emsp;Type: [String](../datatypes/devenv-text-data-type.md)  
The local name of the attribute to retrieve.  
  
*NamespaceUri*    
&emsp;Type: [String](../datatypes/devenv-text-data-type.md)  
The namespace URI of the attribute to retrieve.  
  
*Result*    
&emsp;Type: [XmlAttribute](xmlattribute-class.md)   
Variable containing the requested XmlAttribute if the operation is successful.  
  
## Return Value
*Ok*  
&emsp;Type: [Boolean](../datatypes/devenv-boolean-data-type.md)  
**True** if the operation was successful; otherwise, **false**.  
If you omit this optional return value and the operation does not execute successfully, a run-time error will occur.  
  
## See Also
[XmlAttributeCollection](xmlattributecollection-class.md)  
[XmlAttribute](xmlattribute-class.md)  
[HTTP, JSON, TextBuilder, and XML API](../devenv-restapi-overview.md)  
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions Using the New Development Environment](../devenv-dev-overview.md)  

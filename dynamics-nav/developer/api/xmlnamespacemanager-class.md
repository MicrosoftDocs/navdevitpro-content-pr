---
title: "XmlNamespaceManager Class"
ms.author: solsen
ms.custom: na
ms.date: 07/20/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 620f0e32-eadc-43e9-8f6e-8fc0b12c3aaf
caps.latest.revision: 1
manager: edupont
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# XmlNamespaceManager Class
Resolves, adds, and removes namespaces to a collection and provides scope management for these namespaces.

The following methods are available on the XmlNamespaceManager class.  
  
|Method name|Description|  
|-----------|-----------|  
|[XmlNamespaceManager.NameTable(XmlNameTable)](xmlnamespacemanager-nametable-property.md)|Gets or sets the XmlNameTable associated with this object.|  
|[XmlNamespaceManager.AddNamespace(String, String)](xmlnamespacemanager-addnamespace-method.md)|Adds the given namespace to the collection.|  
|[XmlNamespaceManager.HasNamespace(String)](xmlnamespacemanager-hasnamespace-method.md)|Gets a value indicating whether the supplied prefix has a namespace defined for the current pushed scope.|  
|[XmlNamespaceManager.LookupNamespace(String, Text)](xmlnamespacemanager-lookupnamespace-method.md)|Gets the namespace URI for the specified prefix.|  
|[XmlNamespaceManager.LookupPrefix(String, Text)](xmlnamespacemanager-lookupprefix-method.md)|Finds the prefix declared for the given namespace URI.|  
|[XmlNamespaceManager.RemoveNamespace(String, String)](xmlnamespacemanager-removenamespace-method.md)|Removes the given namespace for the given prefix.|  
|[XmlNamespaceManager.PushScope()](xmlnamespacemanager-pushscope-method.md)|Pushes a namespace scope onto the stack.|  
|[XmlNamespaceManager.PopScope()](xmlnamespacemanager-popscope-method.md)|Pops a namespace scope off the stack.|  
## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  
[HTTP, JSON, and XML API](../devenv-restapi-overview.md)  

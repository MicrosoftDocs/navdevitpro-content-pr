---
title: "XmlText Class"
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

# XmlText Class
Represents the text content of an element or attribute.

The following methods are available on the XmlText class.  
  
|Method name|Description|  
|-----------|-----------|  
|[XmlText.Create(String)](xmltext-create-method.md)|Creates an XmlText node.|  
|[XmlText.Value(String)](xmltext-value-property.md)|Gets or sets the value of this node.|  
|[XmlText.AsXmlNode()](xmltext-asxmlnode-method.md)|Converts the node to an XmlNode.|  
|[XmlText.GetParent(XmlElement)](xmltext-getparent-method.md)|Gets the parent XmlElement of this node.|  
|[XmlText.GetDocument(XmlDocument)](xmltext-getdocument-method.md)|Gets the XmlDocument for this node.|  
|[XmlText.AddAfterSelf(Joker)](xmltext-addafterself-method.md)|Adds the specified content immediately after this node.|  
|[XmlText.AddBeforeSelf(Joker)](xmltext-addbeforeself-method.md)|Adds the specified content immediately before this node.|  
|[XmlText.ReplaceWith(Joker)](xmltext-replacewith-method.md)|Replaces this node with the specified content.|  
|[XmlText.Remove()](xmltext-remove-method.md)|Removes this node from its parent element.|  
|[XmlText.WriteTo(OutStream)](xmltext-writeto-outstream-method.md)|Serializes and saves the current node to the given variable.|  
|[XmlText.WriteTo(Text)](xmltext-writeto-text-method.md)|Serializes and saves the current node to the given variable.|  
|[XmlText.SelectSingleNode(String, XmlNode)](xmltext-selectsinglenode-xpath-node-method.md)|Selects the first XmlNode that matches the XPath expression.|  
|[XmlText.SelectSingleNode(String, XmlNamespaceManager, XmlNode)](xmltext-selectsinglenode-xpath-namespacemanager-node-method.md)|Selects the first XmlNode that matches the XPath expression.|  
|[XmlText.SelectNodes(String, XmlNodeList)](xmltext-selectnodes-xpath-nodelist-method.md)|Selects a list of nodes matching the XPath expression.|  
|[XmlText.SelectNodes(String, XmlNamespaceManager, XmlNodeList)](xmltext-selectnodes-xpath-namespacemanager-nodelist-method.md)|Selects a list of nodes matching the XPath expression.|  
## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  
[HTTP, JSON, and XML API](../devenv-restapi-overview.md)  
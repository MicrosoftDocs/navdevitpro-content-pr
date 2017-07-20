---
title: "XmlAttribute Class"
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

# XmlAttribute Class
Represents an attribute.

The following methods are available on the XmlAttribute class.  
  
|Method name|Description|  
|-----------|-----------|  
|[XmlAttribute.Create(String, String)](xmlattribute-create-name-value-method.md)|Creates an XmlAttribute.|  
|[XmlAttribute.Create(String, String, String)](xmlattribute-create-localname-namespaceuri-value-method.md)|Creates an XmlAttribute.|  
|[XmlAttribute.CreateNamespaceDeclaration(String, String)](xmlattribute-createnamespacedeclaration-method.md)|Creates an attribute that represents a namespace declaration.|  
|[XmlAttribute.Name](xmlattribute-name-property.md)|The qualified name of the attribute. |  
|[XmlAttribute.LocalName](xmlattribute-localname-property.md)|The local name of the attribute.|  
|[XmlAttribute.NamespaceUri](xmlattribute-namespaceuri-property.md)|The namespace URI of the attribute.|  
|[XmlAttribute.NamespacePrefix](xmlattribute-namespaceprefix-property.md)|The prefix of the attribute (if any).|  
|[XmlAttribute.IsNamespaceDeclaration](xmlattribute-isnamespacedeclaration-property.md)|Determines if this attribute is a namespace declaration.| 
|[XmlAttribute.Value(String)](xmlattribute-value-property.md)|Gets or sets the value of the attribute.|  
|[XmlAttribute.AsXmlNode()](xmlattribute-asxmlnode-method.md)|Convert the node to an XmlNode.|  
|[XmlAttribute.GetParent(XmlElement)](xmlattribute-getparent-method.md)|Gets the parent XmlElement of this node.|  
|[XmlAttribute.GetDocument(XmlDocument)](xmlattribute-getdocument-method.md)|Gets the XmlDocument for this node.|  
|[XmlAttribute.AddAfterSelf(Joker)](xmlattribute-addafterself-method.md)|Adds the specified content immediately after this node.|  
|[XmlAttribute.AddBeforeSelf(Joker)](xmlattribute-addbeforeself-method.md)|Adds the specified content immediately before this node.|  
|[XmlAttribute.ReplaceWith(Joker)](xmlattribute-replacewith-method.md)|Replaces this node with the specified content.|  
|[XmlAttribute.Remove()](xmlattribute-remove-method.md)|Removes this attribute from its parent element.|  
|[XmlAttribute.WriteTo(OutStream)](xmlattribute-writeto-outstream-method.md)|Serializes and saves the current node to the given variable.|  
|[XmlAttribute.WriteTo(Text)](xmlattribute-writeto-text-method.md)|Serializes and saves the current node to the given variable.|  
|[XmlAttribute.SelectSingleNode(String, XmlNode)](xmlattribute-selectsinglenode-xpath-node-method.md)|Selects the first XmlNode that matches the XPath expression.|  
|[XmlAttribute.SelectSingleNode(String, XmlNamespaceManager, XmlNode)](xmlattribute-selectsinglenode-xpath-namespacemanager-node-method.md)|Selects the first XmlNode that matches the XPath expression.|  
|[XmlAttribute.SelectNodes(String, XmlNodeList)](xmlattribute-selectnodes-xpath-nodelist-method.md)|Selects a list of nodes matching the XPath expression.|  
|[XmlAttribute.SelectNodes(String, XmlNamespaceManager, XmlNodeList)](xmlattribute-selectnodes-xpath-namespacemanager-nodelist-method.md)|Selects a list of nodes matching the XPath expression.|  

## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

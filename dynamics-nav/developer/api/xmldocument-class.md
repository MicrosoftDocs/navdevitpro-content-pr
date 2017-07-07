---
title: "XmlDocument Class"
ms.author: solsen
ms.custom: na
ms.date: 30/06/2017
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

# XmlDocument Class
Represents an XML document. This class can be used to load, validate, edit, add, and position XML in a document.

The following methods are available on the XmlDocument class.  
  
|Method name|Description|  
|-----------|-----------|  
|[XmlDocument.ReadFrom(String, XmlDocument)](xmldocument-readfrom-text-result-method.md)|Read and parse the XML document from the given data source.|  
|[XmlDocument.ReadFrom(InStream, XmlDocument)](xmldocument-readfrom-instream-result-method.md)|Read and parse the XML document from the given data source.|  
|[XmlDocument.Create()](xmldocument-create--method.md)|Creates an XmlDocument.|  
|[XmlDocument.Create(Joker)](xmldocument-create-content-method.md)|Creates an XmlDocument.|  
|[XmlDocument.GetRoot(XmlElement)](xmldocument-getroot-method.md)|Gets the root element of the XML tree for this document.|  
|[XmlDocument.GetDeclaration(XmlDeclaration)](xmldocument-getdeclaration-method.md)|Gets the XML declaration for this document.|  
|[XmlDocument.SetDeclaration(XmlDeclaration)](xmldocument-setdeclaration-method.md)|Sets the XML declaration for this document.|  
|[XmlDocument.GetDocumentType(XmlDocumentType)](xmldocument-getdocumenttype-method.md)|Gets the Document Type Definition (DTD) for this document.|  
|[XmlDocument.AsXmlNode()](xmldocument-asxmlnode-method.md)|Converts the node to an XmlNode.|  
|[XmlDocument.GetParent(XmlElement)](xmldocument-getparent-method.md)|Gets the parent XmlElement of this node.|  
|[XmlDocument.GetDocument(XmlDocument)](xmldocument-getdocument-method.md)|Gets the XmlDocument for this node.|  
|[XmlDocument.AddAfterSelf(Joker)](xmldocument-addafterself-method.md)|Adds the specified content immediately after this node.|  
|[XmlDocument.AddBeforeSelf(Joker)](xmldocument-addbeforeself-method.md)|Adds the specified content immediately before this node.|  
|[XmlDocument.ReplaceWith(Joker)](xmldocument-replacewith-method.md)|Replaces this node with the specified content.|  
|[XmlDocument.Remove()](xmldocument-remove-method.md)|Removes this node from its parent element.|  
|[XmlDocument.WriteTo(OutStream)](xmldocument-writeto-outstream-method.md)|Serializes and saves the current node to the given variable.|  
|[XmlDocument.WriteTo(Text)](xmldocument-writeto-text-method.md)|Serializes and saves the current node to the given variable.|  
|[XmlDocument.SelectSingleNode(String, XmlNode)](xmldocument-selectsinglenode-xpath-node-method.md)|Selects the first XmlNode that matches the XPath expression.|  
|[XmlDocument.SelectSingleNode(String, XmlNamespaceManager, XmlNode)](xmldocument-selectsinglenode-xpath-namespacemanager-node-method.md)|Selects the first XmlNode that matches the XPath expression.|  
|[XmlDocument.SelectNodes(String, XmlNodeList)](xmldocument-selectnodes-xpath-nodelist-method.md)|Selects a list of nodes matching the XPath expression.|  
|[XmlDocument.SelectNodes(String, XmlNamespaceManager, XmlNodeList)](xmldocument-selectnodes-xpath-namespacemanager-nodelist-method.md)|Selects a list of nodes matching the XPath expression.|  
|[XmlDocument.Add(Joker)](xmldocument-add-method.md)|Adds the specified content as a child of this document.|  
|[XmlDocument.AddFirst(Joker)](xmldocument-addfirst-method.md)|Adds the specified content at the start of the child list of this document.|  
|[XmlDocument.ReplaceNodes(Joker)](xmldocument-replacenodes-method.md)|Replaces the children nodes of this document with the specified content.|  
|[XmlDocument.RemoveNodes()](xmldocument-removenodes-method.md)|Removes the child nodes from this document.|  
|[XmlDocument.GetChildNodes()](xmldocument-getchildnodes-method.md)|Gets a list containing the child elements for this document, in document order.|  
|[XmlDocument.GetChildElements()](xmldocument-getchildelements--method.md)|Gets a list containing the child elements for this document, in document order.|  
|[XmlDocument.GetChildElements(String)](xmldocument-getchildelements-name-method.md)|Gets a list containing the child elements for this document, in document order.|  
|[XmlDocument.GetChildElements(String, String)](xmldocument-getchildelements-localname-namespaceuri-method.md)|Gets a list containing the child elements for this document, in document order.|  
|[XmlDocument.GetDescendantNodes()](xmldocument-getdescendantnodes-method.md)|Gets a list containing the descendant nodes for this document, in document order.|  
|[XmlDocument.GetDescendantElements()](xmldocument-getdescendantelements--method.md)|Gets a list containing the descendant elements for this document, in document order.|  
|[XmlDocument.GetDescendantElements(String)](xmldocument-getdescendantelements-name-method.md)|Gets a list containing the descendant elements for this document, in document order.|  
|[XmlDocument.GetDescendantElements(String, String)](xmldocument-getdescendantelements-localname-namespaceuri-method.md)|Gets a list containing the descendant elements for this document, in document order.|  
## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  

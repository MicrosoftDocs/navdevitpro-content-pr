---
title: "WriteTo_Stream Method"
ms.author: solsen
ms.custom: na
ms.date: 01/08/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 620f0e32-eadc-43e9-8f6e-8fc0b12c3aaf
caps.latest.revision: 9
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# WriteTo_Stream Method
Serializes and writes the JSON data of the JsonArray to a given OutStream object.

```
[Ok := ] JsonArray.WriteTo(var OutStream)
```

### Parameters
*JsonArray*  
&emsp;Type: [JsonArray](jsonarray-class.md)

*OutStream*  
&emsp;Type: [OutStream](/datatypes/devenv-instream-and-outstream-data-types.md)

The OutStream object to which the JSON data will be written.

## Property Value/Return Value
&emsp;Type: [Boolean](../datatypes/devenv-boolean-data-type.md)

**True** if the write was successful; otherwise, **false**.

If you omit this optional return value and if the write does not execute successfully, then a run-time error occurs.

## Example
The following example illustrates how to create a Stream from a Blob and write to a Stream from an XML document.

```
pageextension 50100 CustomerListExt extends "Customer List"
{
    trigger OnOpenPage();
    var
        xmlDoc: XmlDocument;
        xmlDec: XmlDeclaration;
        xmlElem: XmlElement;
        xmlElem2: XmlElement;
        TempBlob: Record TempBlob Temporary;
        outStr: OutStream;
        inStr: InStream;
        TempFile: File;
        fileName: Text;
    begin
        xmlDoc := xmlDocument.Create();
        xmlDec := xmlDeclaration.Create('1.0', 'UTF-8', '');
        xmlDoc.SetDeclaration(xmlDec);

        xmlElem := xmlElement.Create('root');
        xmlElem.SetAttribute('release', '2.1');

        xmlElem2 := XmlElement.Create('FirstName');
        xmlElem2.Add(xmlText.Create('Max'));

        xmlElem.Add(xmlElem2);
        xmlDoc.Add(xmlElem);

        // Create an outStream from the Blob, notice the encoding.
        TempBlob.Blob.CreateOutStream(outStr, TextEncoding::UTF8);

        // Write the contents of the doc to the stream
        xmlDoc.WriteTo(outStr);

         // From the same Blob, that now contains the XML document, create an inStr
        TempBlob.Blob.CreateInStream(inStr, TextEncoding::UTF8);

        // Save the data of the InStream as a file.
        File.DownloadFromStream(inStr, 'Export', '', '', fileName);
    end;
}
```

## See Also
[JsonArray](jsonarray-class.md)  
[HTTP, JSON, TextBuilder, and XML API](../devenv-restapi-overview.md)  
[Getting Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

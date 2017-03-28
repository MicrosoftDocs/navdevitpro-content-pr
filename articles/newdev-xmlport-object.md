---
title: "XMLport Object"
description: "Description of the xmlport object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 03/24/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: SusanneWindfeldPedersen
caps.latest.revision: 18
---

[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/newdev_dev_preview.md)]

# XMLport Object
XMLports are used to export and import data between an external source and a Dynamics for Financials database. 

## Snippet support
Typing the shortcut ```txmlport``` will create the basic layout for an XMLport object when using the AL Extension in Visual Studio Code.

## XMLport example
The following example is a ...

```
xmlport id MyXmlport
{
    schema
    {
        textelement(NodeName1)
        {
            tableelement(NodeName2; TableName)
            {
                fieldattribute(NodeName3; TableName.FieldName)
                {
                }
            }
        }
    }

    requestpage
    {
        layout
        {
            area(content)
            {
                group(GroupName)
                {
                    field(Name;NameSource)
                    {
                        
                    }
                }
            }
        }
    
        actions
        {
            area(processing)
            {
                action(ActionName)
                {
                    trigger OnAction();
                    begin
                    end;
                }
            }
        }
    }
}
```

## See Also
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)  
[Developer Reference](newdev-reference-overview.md)  
[Page Extension Object](newdev-page-ext-object.md)  
[Report Object](newdev-report-object.md)  
[Pages](pages.md)  
[Tables](tables.md)  
[Page Properties](page-properties.md)

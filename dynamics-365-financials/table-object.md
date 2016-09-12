---
title: "Table Object"
description: "Description of the table object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 09/07/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
caps.latest.revision: 18
---
# Table Object
The table object contains the definition of fields, groups, triggers, and metadata. A table object definition can contain the following elements (mandatory marked):

+ 
+ 
+  



## Examples

```



table 50000 Address
{
    fields
    {
        field(1;Address;Text[50])
        {
            Description='Address retrieved by Service';
        }
        field(2;Locality;Text[30])
        {
            Description='Locality retrieved by Service';
        }
        field(3;"Town/City";Text[30])
        {
            Description='Town/City retrieved by Service';
        }
        field(4;County;Text[30])
        {
            Description='County retrieved by Service';
        } 
    }
    keys
    {
        key(1;PrimaryKey;Address)
        {
            Clustered=TRUE;
        }
    }
}
``` 
  
## Remarks  
  
## See Also  
 [Pages](../dynamics-nav/Pages.md)   
 [How to: Create a Page](../dynamics-nav/How%20to:%20Create%20a%20Page.md)   
 [Properties](../dynamics-nav/Properties.md)

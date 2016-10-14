---
title: "StyleExpr Property"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 6400d515-9f4e-4422-a89e-99100bf9110c
caps.latest.revision: 18
manager: edupont
---
# StyleExpr Property
Sets whether the format that is specified in the [Style Property](Style-Property-duplicate.md) is applied to text in a field. For fields in a **CueGroup** control, this property is used to configure the color of the color indicator on the cue.  

> [!IMPORTANT]  
>  This note pertains to backward compatibility only. If the property is set to Boolean true or false, it sets whether the format specified in the **Style** property is applied to text in a field.  

## Applies To  

-   Page field controls that are not of data type Boolean or BLOB.  

-   Field controls in **CueGroups** of data type Boolean, Text, or Codeunit.  

## Remarks  

> [!NOTE]  
>  The information in this topic is mainly applicable to formatting the text of page fields. For information about how to use the **StyleExpr** property for configuring Cues, see [How to: Set Up Colored Indicators on Cues by Using the Style and StyleExpr Property](How-to--Set-Up-Colored-Indicators-on-Cues-by-Using-the-Style-and-StyleExpr-Property.md).  

 You can set **StyleExpr** to either the name of a variable; a text constant in apostrophes, for example, 'strong'; or, for backward compatibility, to **true** or **false**.  

 If the **StyleExpr** property evaluates to **true**, then the value of the field is formatted as specified by the [Style Property](Style-Property-duplicate.md). You can set the value to **true** or **false**, or you can use a variable that evaluates to **true** or **false**. The property's default value is **false**.  

> [!IMPORTANT]  
>  You can use a conditional setting of styles by inserting the conditional code in, for example, the [OnAfterGetRecord Trigger](OnAfterGetRecord-Trigger.md). Remember to cover all cases in else branches to avoid incorrect styles. For example: `if (MyField = 'abc') then   MyStyleVar := 'Ambiguous' else   MyStyleVar := 'Favorable'`  

> [!NOTE]  
>  To use a variable for the **StyleExpr** property, the [IncludeInDataSet Property](IncludeInDataSet-Property.md) of the variable must be set to **Yes**.  

## See Also  
 [How to: Style Field Text on a Page](How-to--Style-Field-Text-on-a-Page.md)

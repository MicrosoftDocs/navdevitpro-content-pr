---
title: "GroupType Property"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 349e71ab-2fe0-457a-84de-9281de73d070
caps.latest.revision: 18
---
# GroupType Property
Sets the subtype for a group control on a page, which determines how fields in a group layout on a page.  
  
## Applies To  
  
-   Group type controls on pages  
  
## Property Values  
  
|Value|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|For more information|  
|-----------|---------------------------------------|--------------------------|  
|**Group**|If the control is a top level control that does not have a child group of the subtype **CueGroup**, **FixedLayout**, or **GridLayout**, then the **Group** setting creates a FastTab of fields; otherwise, it is acts as a container for the child group.|[How to: Add FastTabs to a Customer Card Page](../Topic/How%20to:%20Add%20FastTabs%20to%20a%20Customer%20Card%20Page.md)|  
|**Repeater**|Arranges fields in a row and repeats the fields on subsequest lines in a table. This is used for displaying data in a list, such as Sales Orders or Customers.|[Walkthrough: Creating a Customer List in Page Designer](../Topic/Walkthrough:%20Creating%20a%20Customer%20List%20in%20Page%20Designer.md)|  
|**CueGroup**|Displays fields as a Cue on page. A Cue is a graphical representation of a total number of entities in a database table. This is typically only used on Role Center page types.|[Walkthrough: Creating a Cue Based on a FlowField](../Topic/Walkthrough:%20Creating%20a%20Cue%20Based%20on%20a%20FlowField.md)|  
|**FixedLayout**|Arranges fields in rows and columns.<br /><br /> This value is not fully supported by the [!INCLUDE[nav_web](includes/nav_web_md.md)]. You can experience misalignment of captions and fields in some setups.|[Arranging Fields in Rows and Columns Using a FixedLayout Control](Arranging-Fields-in-Rows-and-Columns-Using-a-FixedLayout-Control.md)|  
|**GridLayout**|Arranges fields in rows and columns. **GridLayout** gives you more control than **FixedLayout** over how fields are displayed by letting you span rows and columns, specify labels for individual fields, and layout fields in a row\-by\-row or column\-by\-column basis.<br /><br /> This value is not fully supported by the [!INCLUDE[nav_web](includes/nav_web_md.md)]. You cannot span rows and columns by setting the [RowSpan Property](RowSpan-Property.md) and [ColumnSpan Property](ColumnSpan-Property.md) on fields because these properties are not supported.|[How to: Arrange Fields in Rows and Columns Using the GridLayout Control](../Topic/How%20to:%20Arrange%20Fields%20in%20Rows%20and%20Columns%20Using%20the%20GridLayout%20Control.md)|
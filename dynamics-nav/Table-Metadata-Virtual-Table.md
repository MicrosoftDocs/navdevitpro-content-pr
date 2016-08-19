---
title:"Table Metadata Virtual Table"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod:"dynamics-nav-2017"
ms.assetid: 40de1a1b-a7cd-4cd6-8de4-7d14b87f6876
caps.latest.revision: 9
manager: edupont
---
# Table Metadata Virtual Table
The **Table Metadata** virtual table \(ID 2000000136\) contains data about the tables in database. The following table describes the fields in the **Table Metadata** virtual table.  
  
|[!INCLUDE[bp_tablefield](includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|---------------------------------|---------------------------------------|  
|**TableNo**|The ID for the table object.|  
|**Table Name**|Specifies the name of the table object.|  
|**Caption**|Specifies the caption of the table in the language that has been selected.|  
|**DataPerCompany**|Sets whether the table data applies to only the current company \(**No**\) or all companies \(**Yes**\) in the database.|  
|**LookupPageID**|Specifies the ID of the page that is used for lookup.|  
|**DrilldownPageID**|Specifies the ID of the page that is used for drill down.|  
|**DataCaption Fields**|Specifies one or more fields that will be used as captions when a record from this table is displayed in a page.|  
|**PasteIsValid**|Specifies whether inserting records into this table using the paste command is enabled.|  
|**LinkedObject**|Specifies whether to link to SQL Server objects.|  
|**DataIsExternal**|Specifies whether the data is from an external table which means that the data is not managed by [!INCLUDE[navnow](includes/navnow_md.md)].<br /><br /> **DataIsExternal** is set if the [LinkedObject Property](LinkedObject-Property.md) is set to **Yes** or the [TableType Property](TableType-Property.md) is set to **CRM** or **ExternalSQL** .|  
|TableType|Specifies whether the table type is **Normal**, **CRM**, or **ExternalSQL**.|  
  
 Except for the **DataIsExternal** field, the fields in the virtual table correspond directly to C\/AL properties on the table objects. For more information, see [Table Properties](Table-Properties.md).  
  
 To access and view the **Table Metadata** virtual table, you must create a tabular\-type page. For more information, see [How to: Create a Page to View a Virtual Table](../Topic/How%20to:%20Create%20a%20Page%20to%20View%20a%20Virtual%20Table.md)  
  
## See Also  
 [Virtual Tables](Virtual-Tables.md)
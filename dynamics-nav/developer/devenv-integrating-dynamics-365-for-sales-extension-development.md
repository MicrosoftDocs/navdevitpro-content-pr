---
title: Enabling Sales Tables for Extension Development
description: This topic explains how to enable Dynamics 365 for Sales tables for the extension development process.
ms.custom: na
ms.date: 02/20/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 096dd046-161f-4d06-8212-0804f4271590
caps.latest.revision: 13
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# Integrating Dynamics 365 for Sales for Extension Development

Develop extensions and streamline the workflow by synchronizing the Sales data from Microsoft Dynamics 365 for Sales with [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] and [!INCLUDE[navnow_md](../includes/navnow_md.md)]. 

For developing extensions to integrate with sales data, you simply enable the tables used in Dynamics 365 for Sales. The extension development process includes the following set of properties to enable field mapping.
You can enable the field mapping by using the following properties. 

## Associated table and field properties

The following properties are used for integrating with Microsoft Dynamics 365 for Sales:

|Properties | Applies to | Description |
|-----------|------------|-------------|
|[TableType Property](properties/devenv-tabletype-property.md)|Tables |Specifies the table type. This enables the table to integrate with the external database. For example, `CRM`. |
|[ExternalName Property](properties/devenv-externalname-property.md)|Tables, Fields|Specifies the name of the original table in the external database when used as a table property.</br> <br>Specifies the field name of the corresponding field specified in the external table when used as a field property.</br> | 
|[ExternalAccess Property](properties/devenv-externalaccess-property.md)|Fields|Specifies the access to the underlying CRM entity when CRM tables are generated using the cmdlet.|
|[ExternalType Property](properties/devenv-externaltype-property.md)|Fields|Specifies the data type of the corresponding field in Dynamics 365 for Sales table. |
|[OptionMembers Property](properties/devenv-optionstring-property.md)|Fields|Sets the option values for a field, text box or variable. | 
|[OptionOrdinalValues Property](properties/devenv-optionordinalvalues-property.md)|Fields|Specifies the list of option values. You can set this property, if the ExternalType is set to Picklist.| 

## Enabling the entity
Typically in Dynamics 365 for Sales, entities handle the internal processes. In order to access to the underlying CRM entity, you use the TableType property and select the value called **CRM**. This enables the table as an integration table for integrating [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] and [!INCLUDE[navnow_md](../includes/navnow_md.md)] with Dynamics 365 for Sales. The table is mainly based on an entity in Dynamics 365 for Sales, such as the Accounts entity.

## Snippet support
Typing the shortcut `ttable` will create the basic layout for a table object when using the AL Extension in Visual Studio Code. 

## Example 
In the following example, the `SalesIntegration` table uses the TableType and ExternalName properties to link the underlying **CRM** entity for mapping the fields from the `Sales` table with the specified fields. 

```
table 50100 SalesIntegration
{
    TableType = CRM;
    ExternalName = 'Sales';

    fields
    {
        field(1; ActualSales; Integer)
        {
            ExternalName = 'ActualSale';
            ExternalAccess = Full;
            ExternalType = 'String';                        
        }

        field(2; SalesCategories; Option)
        {
            ExternalName='SalesCategory';
            ExternalAccess = Read;                        
            ExternalType = 'Picklist';
            OptionMembers = Manufacturing, Marketing, Support;
            OptionOrdinalValues = -1, 1, 2;
        }
    }
}
```

## See Also
[Table Properties](properties/devenv-table-properties.md)  
[TableType Property](properties/devenv-tabletype-property.md)  
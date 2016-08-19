---
title:"Formatting the Data in a Field"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod:"dynamics-nav-2017"
ms.assetid: b54bf548-379f-4724-8901-12ab3ba5d181
caps.latest.revision: 11
manager: edupont
---
# Formatting the Data in a Field
This topic describes how you can format the appearance of decimal data types in fields of a table, report, or page. For example, you can change how the data appears in a Cue on the Role Center page. To format data, you use a combination of the [AutoFormatType Property](AutoFormatType-Property.md), [AutoFormatExpr Property](AutoFormatExpr-Property.md), and [DecimalPlaces Property](DecimalPlaces-Property.md) of the field. These properties work together to enable you to specify the following:  
  
-   Display amounts and unit amounts in another currency.  
  
-   Specify the number of decimal places.  
  
-   Specify whether to display a thousand separator.  
  
-   Specify characters before and after the value, such as currency signs or %.  
  
## Implementation Overview  
 When you use the **AutoFormatType** and **AutoFormatExpr** properties to format a field, a trigger called **AutoFormatTranslate** in codeunit 1 is called. **AutoFormatTranslate** has ID 12 and takes two parameters: one from the AutoFormatType property and one from the AutoFormatExpr property. The AutoFormatType property can contain one of the following integers: 0, 1, 2, or 10. These settings are described in the next section.  
  
 When a field appears on a page or report, you can set the **AutoFormatType** and **AutoFormatExpr** properties directly on the page field or report field \(column\), or you can set them on the underlying table field. If you specify the properties on the table field, then format applies wherever the field is used. Specifying the properties on the page or report field will only apply the format on the specific page or report. If you specify the properties on the table field and the page or report field, then the settings on the page or report field take precedence.  
  
 You can see an example implementation of the AutoFormatType logic in the [!INCLUDE[demolong](includes/demolong_md.md)]. In the [!INCLUDE[demolong](includes/demolong_md.md)], the **AutoFormatTranslate** trigger calls codeunit **45 AutoFormatManagement** which handles the formatting.  
  
## Setting up Data Formatting  
 The settings for the **AutoFormatType**, **AutoFormatExpr**, and **DecimalPlaces** properties will depend on the type of data that is displayed, such as currency amounts and unit amounts or other types of data, such as simple decimals or ratios. For the most part, the **AutoFormatType** property is the primary setting which determines the options for setting the **DecimalPlaces** and **AutoFormatExpr** properties.  
  
 The following table describes how to set each of the properties to achieve the format that you want.  
  
|**AutoFormatType Property**|**DecimalPlaces Property**|**AutoFormatExpr Property**|**Usage Description**|  
|---------------------------------|--------------------------------|---------------------------------|---------------------------|  
|0|Set to the number of decimal places that you want to display for the value.|Not applicable. This property is ignored.|Use this configuration when you want to format the decimal value according the Standard Format 0 \(which is the default format\) with a specific number of decimal places.<br /><br /> For example, if the value is a US decimal **\-76543.21** and you set the **DecimalPlaces** property to **0**, then the value appears as **76,543**.|  
|1|Not applicable. This property is ignored.|Set to return a currency code \(the blank currency code denotes LCY\).|Use this configuration when you want to format the data as an amount. For example, a sales order will use two decimals when the currency is defined as US dollar and 0 decimals when the currency is defined as IDR \(Indonesian rupiah\).|  
|2|Not applicable. This property is ignored.|Set to return a currency code \(the blank currency code denotes LCY\).|This is similar to the previous configuration where the **AutoFormatType** property is set to 1, except you use this configuration when you want to format the data as a unit amount.|  
|10|Not applicable. This property is ignored.|Set to the property according to the following syntax:<br /><br /> `'[Characters]<precision, N:N><standard format, N>[Characters]'`<br /><br /> Replace `[Characters]` with the text that you want before or after the value, such as $ or %.<br /><br /> `<standard format, N>` specifies which of the standard formats to use. Replace `N` with the format that you want. For more information, see [Standard Formats](Formatting-the-Data-in-a-Field.md#StandardFormats).<br /><br /> `<precision n:N>` species the decimal places, where `n` is the minimum number of decimal places and `N` is the maximum number of decimal places.|Use this configuration if you want to customize the format based on one of the standard formats. This option enables you to specify characters before and after the decimal value, such as currency signs \($\) and percent \(%\).<br /><br /> For example, if you want to prefix the decimal value with a "$", include a thousand separator, and have a maximum of two decimal places \(such as $76,543.21\), then you can set the property to the following:<br /><br /> `$<precision, 2:2><standard format, 0>'`<br /><br /> If you want to display the decimal value as a percentage, then you can add "%" at the end of the setting, for example, `'<precision,1:1><Standard Format,0>%'`. When you include a "%" at the end of the setting, then the decimal value is assumed to be a ratio and the decimal value will be multiplied by 100. For example, a value of 0.98 will be formatted to 98%.|  
  
##  <a name="StandardFormats"></a> Standard Formats  
 The following table describes the standard formats that are available for the **AutoFormatExpr** property when the **AutoFormatType** property is set to 10.  
  
|**Standard Format**|**Format Description**|**Europe Decimal Example**|**US Decimal Example**|  
|-------------------------|----------------------------|--------------------------------|----------------------------|  
|0|\<Sign\>\<Integer Thousand\>\<Point or Comma\>\<Decimals\>|\-76.543,21|\-76,543.21|  
|1|\<Sign\>\<Integer\>\<Point or Comma\>\<Decimals\>|\-76543,21|\-76543.21|  
|2|\<Sign\>\<Integer\>\<Point or Comma\>\<Decimals\>|\-76543.21|\-76543.21|  
|3|\<Integer Thousand\>\<Point or Comma\>\<Decimals\>\<Sign\>|76.543,21\-|76,543.21\-|  
|4|\<Integer\>\<Decimals\>\<Point or Comma\>\<Sign\>|76543,21\-|76543.21\-|  
|9|XML format|\-76543.21|\-76543.21|  
  
## See Also  
 [AutoFormatType Property](AutoFormatType-Property.md)   
 [AutoFormatExpr Property](AutoFormatExpr-Property.md)   
 [DecimalPlaces Property](DecimalPlaces-Property.md)   
 [Creating and Customizing Cues](Creating-and-Customizing-Cues.md)
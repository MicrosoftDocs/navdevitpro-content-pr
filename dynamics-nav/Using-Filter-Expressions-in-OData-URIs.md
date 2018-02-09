---
title: "Using Filter Expressions in OData URIs"
author: edupont04
ms.author: edupont
ms.custom: na
ms.date: 05/01/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: e594076a-21e3-4f4d-8760-581cb2b89b1f
manager: edupont
---
# Using Filter Expressions in OData URIs
You can use filter expressions in OData URIs to limit the results that are returned in an AtomPub document. This topic identifies the filter expressions that you can use, describes the equivalent field or table filter that you can use in C/AL, and presents examples to show the syntax for using filter expressions in OData web service URIs and applications.  

## Filter Expressions  
 To add a filter to an OData URI, add `$filter=` to the end of the name of the published web service. For example, the following URI filters the **City** field in the **Customer** page to return all customers who are located in Miami:  

```  
http://localhost:7048/DynamicsNAV/OData/Company('CRONUS International Ltd.')/Customer?$filter=City eq 'Miami'  
```  

 The following table shows the filters that are supported in [!INCLUDE[navnow](includes/navnow_md.md)] OData web services and the equivalent C/AL filter expressions. All examples are based either on page 21, Customer \(published as **Customer**\), or on page 20, General Ledger Entry \(published as **GLEntry**\).  

> [!NOTE]  
>  Filters that do not have equivalent C/AL expressions might take longer to process compared to filters that do have equivalent C/AL expressions. The reason is that filters that do not have equivalent C/AL expressions are processed on the [!INCLUDE[nav_server](includes/nav_server_md.md)] tier, while filters that do have equivalent C/AL expressions are processed on the [!INCLUDE[navnow](includes/navnow_md.md)] database tier.  

|Definition|Example and explanation|Equivalent C/AL expression|  
|----------------|-----------------------------|---------------------------------|  
|Select a range of values|`filter=Entry_No gt 610 and Entry_No lt 615`<br /><br /> Query on GLEntry service. Returns entry numbers 611 through 614.|..|  
|And|`filter=Country_Region_Code eq 'ES' and Payment_Terms_Code eq '14 DAYS'`<br /><br /> Query on Customer service. Returns customers in Spain where Payment\_Terms\_Code=**14 DAYS**.|&|  
|Or|`filter= Country_Region_Code eq 'ES' or Country_Region_Code eq 'US'`<br /><br /> Query on Customer service. Returns customers in Spain and the United States.<br /><br /> **Alert:** You can use OR operators to apply different filters on the same field. However, you cannot use OR operators to apply filters on two different fields.|&#124;|  
|Less than|`filter=Entry_No lt 610`<br /><br /> Query on GLEntry service. Returns entry numbers that are less than 610.|\<|  
|Greater than|`filter= Entry_No gt 610`<br /><br /> Query on GLEntry service. Returns entry numbers 611 and higher.|>|  
|Greater than or equal to|`filter=Entry_No ge 610`<br /><br /> Query on GLEntry service. Returns entry numbers 610 and higher.|>=|  
|Less than or equal to|`filter=Entry_No le 610`<br /><br /> Query on GLEntry service. Returns entry numbers up to and including 610.|\<=|  
|Different from \(not equal\)|`filter=VAT_Bus_Posting_Group ne 'EXPORT'`<br /><br /> Query on Customer service. Returns all customers with VAT\_Bus\_Posting\_Group not equal to EXPORT.|\<>|  
|endswith|`filter=endswith(VAT_Bus_Posting_Group,'RT')`<br /><br /> Query on Customer service. Returns all customers with VAT\_Bus\_Posting\_Group values that end in RT.|\*|  
|startswith|`filter=startswith(Name, 'S')`<br /><br /> Query on Customer service. Returns all customers names beginning with “S”.||  
|substringof|`filter=substringof(Name, ‘urn’)`<br /><br /> Query on Customer service. Returns customer records for customers with names containing the string “urn”.||  
|indexof|`filter=indexof(Location_Code, ‘BLUE’) eq 0`<br /><br /> Query on Customer service. Returns customer records for customers having a location code beginning with the string BLUE.||  
|replace|`filter=replace(City, 'Miami', 'Tampa') eq 'CODERED'`||  
|substring|`filter=substring(Location_Code, 5) eq 'RED'`<br /><br /> Query on Customer service. Returns true for customers with the string RED in their location code starting as position 5.||  
|tolower|`filter=tolower(Location_Code) eq 'code red'`||  
|toupper|`filter=toupper(FText) eq '2ND ROW'`||  
|trim|`filter=trim(FCode) eq 'CODE RED'`||  
|concat|`filter=concat(concat(FText, ', '), FCode) eq '2nd row, CODE RED'`||  
|round|`filter=round(FDecimal) eq 1`||  
|floor|`filter=floor(FDecimal) eq 0`||  
|ceiling|`filter=ceiling(FDecimal) eq 1`||  

## Referencing Different Data Types in Filter Expressions  
 You must use the appropriate notation for different data types with filter expressions.  

-   String values must be delimited by single quotation marks.  

-   Numeric values require no delimiters.  

For more information about data types and other information about conventions and standards for OData URIs, see [Atom Publishing Protocol: URI Conventions](http://go.microsoft.com/fwlink/?LinkId=214635). Conventions for data types are addressed in section 2.2.2, "Abstract Type System."  

## See Also  
 [OData Web Services](OData-Web-Services.md)

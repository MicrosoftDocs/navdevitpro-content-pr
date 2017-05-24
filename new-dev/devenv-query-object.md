---
title: "Query Object"
description: "Description of the query object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 04/26/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: SusanneWindfeldPedersen
caps.latest.revision: 18
---

 

# Query Object

A query describes a dataset of [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. You can query to retrieve fields from a single table or multiple tables. You can specify how to join tables in the query and filter the result data, and you can specify totaling methods on fields, such as sums and averages. Queries retrieve records from one or more tables and combine the records into rows and columns in a single dataset. You create a query by adding a Query object file to your project. In the Query object, you define dataitem and column elements in the elements section. The dataitem element specifies the table to retrieve records from. The column element specifies a field of the table to include in the resulting dataset of a query. 

When you have specified the dataitem and column elements, you create links between the dataitem elements. A dataitem link determines which records to include in the dataset based on a common field between two dataitems.

## Snippet support
Typing the shortcut ```tquery``` will create the basic layout for a Query object when using the AL Extension in Visual Studio Code.

## Query example
The following example shows a query that displays a list of customers with sales and profit figures. The query primarily retrieves fields from the **Customer** table, but also displays fields from the **Salesperson Purchaser** and **Country Region** tables.

The query also uses the DataItemLink property to create a link between the **Customer** table, **Salesperson Code** field and the **Salesperson Purchaser** table, **Code** fields and a link between the **Customer** table, **Country/Region Code** field and the **Country/Region** table, **Code** field. 

```
query 100 "Top Customer Overview"
{
  CaptionML=ENU='Top Customer Overview';

  elements
  {
    dataitem(Customer;Customer)
    {
      column(Name;Name)
      {
      }
      column(No;"No.")
      {
      }
      column(Sales_LCY;"Sales (LCY)")
      {
      }
      column(Profit_LCY;"Profit (LCY)")
      {
      }
      column(Country_Region_Code;"Country/Region Code")
      {
      }
      column(City;City)
      {
      }
      column(Global_Dimension_1_Code;"Global Dimension 1 Code")
      {
      }
      column(Global_Dimension_2_Code;"Global Dimension 2 Code")
      {
      }
      column(Salesperson_Code;"Salesperson Code")
      {
      }
      dataitem(Salesperson_Purchaser;"Salesperson/Purchaser")
      {
        DataItemLink=Code=Customer."Salesperson Code";
        column(SalesPersonName;Name)
        {
        }
        dataitem(Country_Region;"Country/Region")
        {
          DataItemLink=Code=Customer."Country/Region Code";
          column(CountryRegionName;Name)
          {
          }
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

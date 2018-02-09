---
title: "SETFILTER Function (Query)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 12b3f553-ca5a-4726-a9d4-3f19daac83d1
caps.latest.revision: 19
manager: edupont
---
# SETFILTER Function (Query)
Sets a filter on a column of a query to limit the records in the resulting dataset of a query.  
  
 The following code shows the syntax of the **SETFILTER** function. *Query* is a variable of the Query data type that specifies the query object.  
  
## Syntax  
  
```  
  
Query.SETFILTER(Column, String[, Value],...)  
```  
  
#### Parameters  
 *Column*  
 Type: Text  
  
 The name of the column in the query that you want to filter. The name is defined by the column's [Name Property](Name-Property.md) in Query Designer.  
  
 *String*  
 Type: Text or code  
  
 The filter expression. A valid expression consists of alphanumeric characters and one or more of the following operators: \<, >, \*, &, &#124;, and =. You can use replacement fields \(%1, %2, and so on\) to insert values at run-time. For more information about filter expressions and syntax, see [Entering Criteria in Filters](Entering-Criteria-in-Filters.md).  
  
 *Value*  
 Type: Any  
  
 Replacement values to insert in replacement fields in the filter expression. The data type of *Value* must match the data type of field that is referred to by the *ColumnName*.  
  
## Remarks  
 To apply filters to a dataset, the **SETFILTER** function must be called before the **OPEN**, **SAVEASXML**, and **SAVEASCSV** functions, as shown in the following example. To remove filters from query, you call the [CLEAR Function](CLEAR-Function.md).  
  
```  
Query.SETFILTER(Column1, String);  
Query.OPEN;  
Query.READ;  
CLEAR(Query);  
```  
  
 A call to the **SETFILTER** function automatically closes a query dataset that is currently open. Therefore, the following code is unauthorized and will fail because there is no open dataset for the **READ** function to read.  
  
```  
Query.OPEN;  
Query.READ;  
Query.SETFILTER(Column2, String);  
Query.READ;  
```  
  
 You can have multiple calls to the **SETFILTER** function. If **SETFILTER** function calls set filters on different columns, then the filters are combined and applied to the dataset. If consecutive **SETFILTER** function calls set filters on the same column, then the last **SETFILTER** function call is applied to the column.  
  
 In addition to the **SETFILTER** function, you can apply filters to a query using the [SETRANGE Function \(Query\)](SETRANGE-Function--Query-.md) function, the **FILTERGROUP** function, and the [DataItemTableFilter Property](DataItemTableFilter-Property.md) and [ColumnFilter Property](ColumnFilter-Property.md) in Query Designer.  
  
|If the **SETFILTER** function...|then...|  
|--------------------------------------|-------------|  
|Sets a filter on the same field as the **DataItemTableFilter** property|The two filters are joined into a resulting filter.|  
|Sets a filter on the same field as the **ColumnFilter** property|The **SETFILTER** function overwrites the **ColumnFilter** property, so the filter that is set by the **SETFILTER** function that is applied to the dataset.|  
|Sets a filter on the same field as the **SETRANGE** function|The function that is called last is applied to the dataset.|  
|Sets a filter on a field that has global filters that are applied by the **FILTERGROUP\(1\)** function|The filters of the **SETFILTER** function are added to the global filters.|  
  
 For example, a query has the following filters set on the **Quantity** column in Query Designer:  
  
-   **DataItemTableFilter** property: Quantity=FILTER\(\<100\)  
  
-   **ColumnFilter** property: Quantity=FILTER\(\<>50\)  
  
 `Query.SETFILTER ("Quantity", '>1’)` will result in a filter that is equivalent to: 1\<Quantity \<100.  
  
 For more information about how to set filters in Query Designer, see [Understanding Query Filters](Understanding-Query-Filters.md).  
  
## Example  
 The following C/AL code example demonstrates how to use the **SETFILTER** function on a query. The example code sets a filter on a query column, and then displays a message when the query is run that indicates the filter on the column.  
  
 This example requires that you do the following:  
  
1.  Create a query called **Customer\_SalesQuantity** that has the following characteristics:  
  
    -   Links table 18, Customer with table 37, Sales Lines from the [!INCLUDE[demolong](includes/demolong_md.md)].  
  
    -   Includes columns for the **Name** and **No.** fields from the **Customer** table and the **Quantity** field from **Sales Lines** table.  
  
         For step-by-step instructions for creating this query, see [Walkthrough: Creating a Query to Link Two Tables](Walkthrough--Creating-a-Query-to-Link-Two-Tables.md).  
  
2.  Create the following C/AL variables and text constant in the object that will run the query, such as a codeunit.  
  
    |Variable name|DataType|Subtype|  
    |-------------------|--------------|-------------|  
    |MyQuery|Query|Customer\_SalesQuantity|  
  
    |Text constant name|ENU Value|  
    |------------------------|---------------|  
    |Text000|Customer name = %1, Quantity = %2|  
  
 The following C/AL code uses the **SETFILTER** function to filter the query dataset on the **Quantity** and **Name** columns. You can add the code to a codeunit, and then run the codeunit to see the results.  
  
```  
// Sets a filter to display only sales quantities greater than 10.  
MyQuery.SETFILTER(Quantity, '>10');  
// Sets a filter to display the columns with the value Selangorian Ltd. only.  
MyQuery.SETFILTER(NAME, 'Selangorian Ltd.');  
// Runs the query.  
MyQuery.OPEN;  
// Reads each row in the dataset and displays message with column values.  
// Stops reading when there are no more rows remaining in the dataset (READ is FALSE).  
WHILE MyQuery.READ DO  
BEGIN  
  MESSAGE(Text000, MyQuery.Name, MyQuery.Quantity);  
END;   
// Saves the resulting dataset as a CSV file.  
MyQuery.SAVEASCSV('c:\temp\CustomerSales.csv');  
// Closes the query.  
Myquery.CLOSE;  
```  
  
 When the code is run, a message that resembles the following appears for each row in the dataset:  
  
 **Customer name = Selangorian Ltd., Quantity = 30**
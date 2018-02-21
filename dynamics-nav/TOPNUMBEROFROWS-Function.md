---
title: "TOPNUMBEROFROWS Function"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: b2e1b0cd-f053-43e4-a7ce-9c4d5be22d83
caps.latest.revision: 14
manager: edupont
---
# TOPNUMBEROFROWS Function
Specifies the maximum number of rows to include in the resulting dataset of a query.  
  
## Syntax  
  
```  
[CurrRows :=] TOPNUMBEROFROWS([NewRows]]  
```  
  
#### Parameters  
 *NewRows*  
 Type: Integer  
  
 The number of rows to include in the resulting dataset. If you do not set the *NewRows* parameter, then the resulting dataset will include all rows.  
  
> [!NOTE]  
>  If you set the value to **0**, then there is no limit and all rows of the dataset are returned.  
  
## Property Value/Return Value  
 Type: Integer  
  
 The number of rows that are included in the dataset.  
  
## Remarks  
 You use the **TOPNUMBEROFROWS** property to limit the resulting dataset to the first set of rows that are generated for the query. For example, you can include only the first 10 or first 100 rows in the resulting dataset. The **TOPNUMBEROFROWS** property is useful for key performance indicators such as the top number of customers or sales.  
  
 You can also specify the number of rows to include in the dataset by setting the [TopNumberOfRows Property](TopNumberOfRows-Property.md) in Query Designer. The **TOPNUMBEROFROWS** function will overwrite the **TopNumberOfRows** property setting.  
  
## Example  
 The following C/AL code example demonstrates how to use the **TOPNUMBEROFROWS** function on a query to return the top 10 customer sales orders based on the quantity of items.  
  
 This example requires that you do the following:  
  
1.  Create a query called **Customer\_SalesQuantity** that has the following characteristics:  
  
    -   Links table **18, Customer** with table **37, Sales Lines** from the [!INCLUDE[demolong](includes/demolong_md.md)].  
  
    -   Includes columns for the **Name** and **No.** fields from the **Customer** table and the **Quantity** field from **Sales Lines** table.  
  
         For step-by-step instructions for creating this query, see [Walkthrough: Creating a Query to Link Two Tables](Walkthrough--Creating-a-Query-to-Link-Two-Tables.md).  
  
    -   The [TopNumberOfRows Property](TopNumberOfRows-Property.md) is set to include only the first 5 rows in the resulting dataset. This setting will be overwritten by the TOPNUMBEROFROWS function.  
  
    -   The [OrderBy Property](OrderBy-Property.md) is set on the Quantity column to sort results in descending order.  
  
2.  Create the following C/AL variables in the object that will run the query.  
  
    |Variable name|DataType|Subtype|  
    |-------------------|--------------|-------------|  
    |MyQuery|Query|Customer\_SalesQuantity|  
    |Counter|Integer|Not applicable|  
  
    |Text constant name|ENU Value|  
    |------------------------|---------------|  
    |Text000|The top number of rows is: %1|  
  
## C/AL Code  
 The following C/AL code runs the query, saves it as a CSV file, and displays a message that states the number of rows that are returned in the resulting dataset. You can add the code as a codeunit, and then run the codeunit to see the results.  
  
```  
// Overwrites the TopNumberOfRows property and returns the first 10 rows in the dataset.  
MyQuery.TOPNUMBEROFROWS(10);  
// Opens the query.  
MyQuery.OPEN;  
// Reads each row of the dataset and counts the number of rows.  
While MyQuery.READ DO  
BEGIN  
  Counter +=1;  
END;  
// Saves the dataset as a CSV file.  
MyQuery.SAVEASCSV('c:\temp\CustomerSales.csv');  
// Displays a message that shows the number of rows.  
MESSAGE(Text000, counter);  
```
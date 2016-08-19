---
title: "SETCURRENTKEY Function (Record)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 216cdb5a-36a1-48dd-90d0-f9f360feccee
caps.latest.revision: 21
manager: terryaus
---
# SETCURRENTKEY Function (Record)
Selects a key for a table.  
  
## Syntax  
  
```  
  
[Ok :=] Record.SETCURRENTKEY(Field1, [Field2],...)  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 The record that contains the fields that identify the key that you want to select. The key can be composed of fields of any supported data type. Data types that are not supported include BLOBs, FlowFilters, variables, and functions.  
  
 *Field1, Field2, …*  
 Type: Field  
  
 One or more fields that identify the key that you want to select.  
  
## Property Value\/Return Value  
 Type: Boolean  
  
 **true** if the key was selected; otherwise, **false**.  
  
 If you omit this optional return value and if the key cannot be found, then a run\-time error occurs. If you include a return value, then you must handle any errors.  
  
## Remarks  
 **SETCURRENTKEY** is used to select a key for a record and set the sort order that is used for the table in question. This key becomes the current key and is used by the [FIND Function \(Record\)](FIND-Function--Record-.md), the [NEXT Function \(Record\)](NEXT-Function--Record-.md), and other functions until another key is selected. Until this function is called, the table's primary key is used as the current key.  
  
 In [!INCLUDE[navnowlong](includes/navnowlong_md.md)], the [CALCFIELDS Function \(Record\)](CALCFIELDS-Function--Record-.md), [CALCSUMS Function \(Record\)](CALCSUMS-Function--Record-.md), AND [CALCSUM Function \(FieldRef\)](CALCSUM-Function--FieldRef-.md) do not require that a SIFT index is defined for the fields that are being calculated. Therefore, you do not need to define keys solely for SIFT indexes. Fewer SIFT indexes and fewer keys can improve performance. In earlier versions of [!INCLUDE[navnow](includes/navnow_md.md)], if a [!INCLUDE[navnow](includes/navnow_md.md)] key that started with the fields that you specified as parameters to **SETCURRENTKEY** did not exist, then you received an error when you called the **SETCURRENTKEY** function. This provided a degree of protection in earlier versions against accidentally requesting a sorting for which no index existed. In [!INCLUDE[navnowlong](includes/navnowlong_md.md)], an index is not required to support a certain sorting, but sorting without an index could lead to bad performance if a search returns a large result set, which would then have to be sorted before the first row is returned.  
  
 Use the following guidelines when you use **SETCURRENTKEY**:  
  
-   Inactive fields are ignored. Only active keys are scanned.  
  
-   When searching for a key, [!INCLUDE[navnow](includes/navnow_md.md)] selects the first occurrence of the specified field\(s\). This means the following:  
  
    -   If you specify only one field as a parameter when you call **SETCURRENTKEY**, then the key that is actually selected may consist of more than one field.  
  
    -   If the field that you specify is the first component of several keys, then the key that is selected is the first one that matches, which may not be the key that you expect.  
  
-   If no keys can be found that include the field\(s\) that you specify, then a run\-time error occurs unless you test the Boolean return value of **SETCURRENTKEY** in your code.  
  
-   If you do test the return value, then you must decide what to do if the function returns **false**, because without a run\-time error, the application continues to run even though no key was found and may fail later.  
  
-   Use only the necessary key fields in a call to **SETCURRENTKEY**. If the definition of the key includes the fields that you specify in the call to **SETCURRENTKEY** in the order given, then you can change the definition of the key without having to change any code. If the table order is not important, then consider one of the following:  
  
    -   If the expected result set is small, then do not call **SETCURRENTKEY** at all. The result will be sorted according to the smallest possible key, which is the primary key.  
  
    -   If the expected result set is large, then call **SETCURRENTKEY** with a field set that matches subsequent calls to **SETRANGE** and **SETFILTER** functions. This way, there is less risk that extra sorting of the large result must be done.  
  
## Example  
 This example shows how to use the **SETCURRENTKEY** function without using a return value. This example requires that you create the following variable.  
  
|Name|DataType|Subtype|  
|----------|--------------|-------------|  
|MyCustomer|Record|Customer|  
  
```  
MyCustomer.SETCURRENTKEY(Name);  
```  
  
 This statement selects the Name key for the **Customer** table. If the key cannot be found, a run\-time error occurs.  
  
## Example  
 This example shows how to use the **SETCURRENTKEY** function with a return value.  
  
 This example requires that you create the following variable.  
  
|Name|DataType|Subtype|  
|----------|--------------|-------------|  
|MyCustomer|Record|Customer|  
  
 This example requires that you create the following text constants.  
  
|Name|ConstValue|  
|----------|----------------|  
|Text000|The key was successfully selected.|  
|Text001|The key could not be found.|  
  
```  
IF MyCustomer.SETCURRENTKEY(Name) THEN  
  MESSAGE(Text000)  
ELSE  
  MESSAGE(Text001);  
```  
  
 By including a return value, you can avoid a run\-time error if a key cannot be found.  
  
## See Also  
 [Record Data Type](Record-Data-Type.md)
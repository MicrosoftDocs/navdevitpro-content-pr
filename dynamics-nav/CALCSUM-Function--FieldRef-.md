---
title: "CALCSUM Function (FieldRef)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 58b46156-fdc3-4ab9-9a3c-abe6fc4fc4ca
caps.latest.revision: 22
manager: edupont
---
# CALCSUM Function (FieldRef)
Calculates the total of all values of a SumIndexField in a table.  
  
## Syntax  
  
```  
  
[Ok :=] FieldRef.CALCSUM  
```  
  
#### Parameters  
 *FieldRef*  
 Type: FieldRef  
  
 Refers to the SumIndexField for which you want to calculate a sum.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 If you omit this optional return value and if the field is not [SumIndexField Technology \(SIFT\)](SumIndexField-Technology--SIFT-.md), then a run-time error occurs. If you include a return value, you must handle any errors.  
  
## Remarks  
 This function is like the [CALCSUMS Function \(Record\)](CALCSUMS-Function--Record-.md) function.  
  
 This function operates only on records that meet the conditions of any filters associated with the record.  
  
 If possible, the CALCSUM function uses SumIndexField Technology \(SIFT\). SIFT is used only if the following conditions are true:  
  
-   The [!INCLUDE[navnow](includes/navnow_md.md)] key contains the fields that are used in the filters that are defined for the FlowField.  
  
-   The SumIndexFields on the [!INCLUDE[navnow](includes/navnow_md.md)] key contain the field to which the FieldRef parameter refers.  
  
-   The [MaintainSIFTIndex Property](MaintainSIFTIndex-Property.md) is set to **Yes**.  
  
    > [!NOTE]  
    >  By default this property is set to **Yes** for all keys.  
  
 For [!INCLUDE[navnowlong](includes/navnowlong_md.md)], CALCSUM execution is decoupled from [!INCLUDE[navnow](includes/navnow_md.md)] SIFT index definitions. This means that if any of the conditions for using SIFT indexes are not true, then [!INCLUDE[navnow](includes/navnow_md.md)] traverses all records in the base table to perform the calculation instead of using SIFT. This can reduce the number of required SIFT indexes, which can improve performance. In earlier versions of [!INCLUDE[navnow](includes/navnow_md.md)], if the conditions for using SIFT indexes were not true and the **MaintainSIFTIndex** property was enabled, then you received an error when you called the CALCSUM function. This provided a degree of protection in earlier versions against accidentally requesting a sorting for which no index existed. In [!INCLUDE[navnowlong](includes/navnowlong_md.md)], an index is not required to support a certain sorting, but sorting without an index could lead to bad performance if a search returns a large result set, which would then have to be sorted before the first row is returned.  
  
 The CALCSUM function adheres to the [SecurityFiltering Property](SecurityFiltering-Property.md). For more information about security filters, see [Record-Level Security](Record-Level-Security.md).  
  
## Example  
 This example sets a RecordRef variable to refer to table 21, the **Cust. Ledger Entry** table. Next, it creates a reference to field 18, the **Sales \(LCY\)** field, in the **Cust. Ledger Entry** table and assigns the field reference to a FieldRef variable. The **Sales \(LCY\)** field is a decimal field and is one of the SumIndexFields on a [!INCLUDE[navnow](includes/navnow_md.md)] key in the **Cust. Ledger Entry** table. The code displays the original value of the FieldRef variable, then calls the CALCSUM function and displays the calculated value of the field.  
  
 This example requires that you create the following variables.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|MyFieldRef|FieldRef|  
|MyRecRef|RecordRef|  
  
```  
MyRecRef.OPEN(21);  
MyFieldRef := MyRecRef.FIELD(18);  
MESSAGE('Before CALCSUM, Sales (LCY) is %1.', MyFieldRef.VALUE);  
MyFieldRef.CALCSUM;  
MESSAGE('After CALCSUM, Sales (LCY) is %1.', MyFieldRef.VALUE);  
```  
  
 On a computer that has the regional format set to English \(United States\), the first message window displays the following:  
  
 **Before CALCSUM, Sales \(LCY\) is 0.**  
  
 The second message window displays the following:  
  
 **After CALCSUM, Sales \(LCY\) is 55,162.67.**  
  
## See Also  
 [CALCSUMS Function \(Record\)](CALCSUMS-Function--Record-.md)
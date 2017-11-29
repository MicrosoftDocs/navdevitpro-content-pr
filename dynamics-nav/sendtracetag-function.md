---
title: "SENDTRACETAG Function"
ms.custom: na
ms.date: 27/11/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
author: jswymer
---
# SENDTRACETAG Function
Assigns a filter to a field that you specify.  
  
## Syntax  
  
```  
SENDTRACETAG(Tag, Category, Verbosity, Message)  
```  
  
#### Parameters  
*Tag*  
 Type: Text or code  
  
The record that contains the field that you want to filter.  
  
*Category*  
Type: Text or code  
  
The field that you want to filter.  
  
*Verbosity*  
Type: Verbosity  
  
Specifies the level of the event as either: Critical, Error, Warning, Normal, Verbose.   
  
*Message*  
Type: Text or code  
  
Specifies the error message of the trace event..  
  
## Remarks  
 If the function is called with a field for which a filter already exists, that filter will be removed before the new one is set. You can construct filters using the following operators:  
  
-   ..   Range  
  
-   &   And  
  
-   &#124;   Or  
  
-   \<   Less than  
  
-   \<=   Less than or equal to  
  
-   >   Greater than  
  
-   >=   Greater than or equal to  
  
-   \<>   Different from  
  
-   \*   Forms a part of value  
  
-   @   Case-insensitive  
  
## Example  
 The following table shows examples of filters.  
  
|Filter|Description|  
|------------|-----------------|  
|A..Z|A range from A to Z|  
|A&#124;G|A or G|  
|F.. & \*A/S|A range from F and A/S is included in the field|  
|\<>B|All except B|  
|\<>''|All not blank|  
|\<=200 &#124; >500|All less than or equal to 200 or greater than 500|  
  
 This example requires that you create the following variable.  
  
|Name|DataType|Subtype|  
|----------|--------------|-------------|  
|GLAccountRec|Record|G/L Account|  
  
```  
// Using a filter with replacement field.  
// This filter selects all accounts in the range from 100 to 200   
//   and No. 300.  
GLAccountRec.SETFILTER("No.", '%1..%2|%3', '100', '200', '300');  
// Using a filter entered directly in a string.  
// This filter, which is entered as a string, has the same result as  
//   the previous example.   
//   This filter selects all accounts in the range from 100 to 200 and   
//   and No. 300.  
GLAccountRec.SETFILTER("No.", '100..200|300');   
```  
  
## See Also  
 [Record Data Type](Record-Data-Type.md)
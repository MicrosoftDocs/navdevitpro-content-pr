---
title: "Variant Data Type"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 98348284-4055-40e2-9bc0-808e95289626
caps.latest.revision: 21
---
# Variant Data Type
The C\/AL variant data type can contain many C\/AL data types or any variants from OCX and Automation objects. However, not all these values can be mapped to C\/AL values. For more information, see [Using COM Technologies in Microsoft Dynamics NAV](../dynamics-nav/Using-COM-Technologies-in-Microsoft-Dynamics-NAV.md).  
  
 The variant data type can contain the following C\/AL data types:  
  
-   Action  
  
-   Automation  
  
-   BigInteger  
  
-   BigText  
  
-   Boolean  
  
-   Byte  
  
-   Char  
  
-   Code  
  
-   Codeunit  
  
-   Date  
  
-   DateFormula  
  
-   DateTime  
  
-   Decimal  
  
-   Duration  
  
-   FilterPageBuilder  
  
-   GUID  
  
-   InStream  
  
-   Integer  
  
-   Option  
  
-   OutStream  
  
-   Record  
  
-   RecordRef  
  
-   Text  
  
-   Time  
  
-   TransactionType  
  
 You can use the variant data type to pass Automation variants from one external component \(Automation or OCX\) to another. This requires that the recipient component can accept the original variant. You can also assign a C\/AL variable to a variant and pass it to an external component. When you pass C\/AL variants ByRef to an external COM component, small conversion differences may occur. Therefore, we recommend that you pass C\/AL variants ByVal if you do not have to assign a new value to the C\/AL variant in your external component.  
  
## Returning Variants in Internal Function Calls  
 The C\/AL variant is a complex data type. To return C\/AL variants in function calls, you must pass them in a parameter ByVar \(called ByRef in COM\).  
  
## Passing DateTime variables to Automation  
 It is not possible to pass a C\/AL DateTime variable to Automation. However, you can convert the C\/AL DateTime to a variant, and then pass it to Automation. The following examples shows how to pass a DateTime to Automation. This example requires that you create the following variables.  
  
|Variable|Data type|  
|--------------|---------------|  
|varAutomation|Automation|  
|varVariant|Variant|  
|varDateTime|DateTime|  
  
```  
varDateTime := CURRENTDATETIME;  
varVariant := varDateTime;  
varAutomation.MethodDateData(varVariant);  
```  
  
## Variants and Approximation  
 A C\/AL variant contains two allocation areas: one for C\/AL variables and one for Automation and OCX variants. This means every time that you assign a C\/AL variable to a variant, the variant will contain the same data as the original variable. The conversion process does not change the data in any way. However, this is not the case with DATI2VARIANT because it is a VT\_VARIANT. When you assign an external variable to a variant, the variant will also contain the same data as the original external variable.  
  
## Assigning Automation Variants to FieldRef Values  
 In [!INCLUDE[navnowlong](../dynamics-nav/includes/navnowlong_md.md)], if an Automation method returns a byte string \(bstr\) in a variant, you cannot assign that variant to a field that is a Code data type. Instead, you must first assign the variant to a code variable, and then assign the code variable to the FieldRef value. For example, the following code assigns a variant from an Automation method to a variable, and then assigns the variable to a field.  
  
```  
CodeVariable := AutomationMetodReturningBStrInVariant();  
FieldRef.Value := CodeVariable;  
```  
  
 In earlier versions of [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)], you could assign the variant to a Code FieldRef value.  
  
## See Also  
 [DATI2VARIANT Function](../dynamics-nav/DATI2VARIANT-Function.md)   
 [ISACTION Function \(Variant\)](../dynamics-nav/ISACTION-Function--Variant-.md)   
 [ISAUTOMATION Function \(Variant\)](../dynamics-nav/ISAUTOMATION-Function--Variant-.md)   
 [ISBINARY Function \(Variant\)](../dynamics-nav/ISBINARY-Function--Variant-.md)   
 [ISBOOLEAN Function \(Variant\)](../dynamics-nav/ISBOOLEAN-Function--Variant-.md)   
 [ISCHAR Function \(Variant\)](../dynamics-nav/ISCHAR-Function--Variant-.md)   
 [ISCODE Function \(Variant\)](../dynamics-nav/ISCODE-Function--Variant-.md)   
 [ISCODEUNIT Function \(Variant\)](../dynamics-nav/ISCODEUNIT-Function--Variant-.md)   
 [ISDATE Function \(Variant\)](../dynamics-nav/ISDATE-Function--Variant-.md)   
 [ISDATEFORMULA Function \(Variant\)](../dynamics-nav/ISDATEFORMULA-Function--Variant-.md)   
 [ISDECIMAL Function \(Variant\)](../dynamics-nav/ISDECIMAL-Function--Variant-.md)   
 [ISFILE Function \(Variant\)](../dynamics-nav/ISFILE-Function--Variant-.md)   
 [ISINSTREAM Function \(Variant\)](../dynamics-nav/ISINSTREAM-Function--Variant-.md)   
 [ISINTEGER Function \(Variant\)](../dynamics-nav/ISINTEGER-Function--Variant-.md)   
 [ISOPTION Function \(Variant\)](../dynamics-nav/ISOPTION-Function--Variant-.md)   
 [ISOUTSTREAM Function \(Variant\)](../dynamics-nav/ISOUTSTREAM-Function--Variant-.md)   
 [ISRECORD Function \(Variant\)](../dynamics-nav/ISRECORD-Function--Variant-.md)   
 [ISTEXT Function \(Variant\)](../dynamics-nav/ISTEXT-Function--Variant-.md)   
 [ISTIME Function \(Variant\)](../dynamics-nav/ISTIME-Function--Variant-.md)   
 [ISTRANSACTIONTYPE Function \(Variant\)](../dynamics-nav/ISTRANSACTIONTYPE-Function--Variant-.md)   
 [VARIANT2DATE Function](../dynamics-nav/VARIANT2DATE-Function.md)   
 [VARIANT2TIME Function](../dynamics-nav/VARIANT2TIME-Function.md)
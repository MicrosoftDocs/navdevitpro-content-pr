---
title: "Variant Data Type"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 98348284-4055-40e2-9bc0-808e95289626
caps.latest.revision: 21
---
# Variant Data Type
The AL variant data type can contain many AL data types or any variants from OCX and Automation objects. However, not all these values can be mapped to AL values. For more information, see [Using COM Technologies in Microsoft Dynamics NAV](Using-COM-Technologies-in-Microsoft-Dynamics-NAV.md).  
  
 The variant data type can contain the following AL data types:  
  
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
  
 You can use the variant data type to pass Automation variants from one external component \(Automation or OCX\) to another. This requires that the recipient component can accept the original variant. You can also assign a AL variable to a variant and pass it to an external component. When you pass AL variants ByRef to an external COM component, small conversion differences may occur. Therefore, we recommend that you pass AL variants ByVal if you do not have to assign a new value to the AL variant in your external component.  
  
## Returning Variants in Internal method Calls  
 The AL variant is a complex data type. To return AL variants in method calls, you must pass them in a parameter ByVar \(called ByRef in COM\).  
  
## Passing DateTime variables to Automation  
 It is not possible to pass a AL DateTime variable to Automation. However, you can convert the AL DateTime to a variant, and then pass it to Automation. The following examples shows how to pass a DateTime to Automation. This example requires that you create the following variables.  
  
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
 A AL variant contains two allocation areas: one for AL variables and one for Automation and OCX variants. This means every time that you assign a AL variable to a variant, the variant will contain the same data as the original variable. The conversion process does not change the data in any way. However, this is not the case with DATI2VARIANT because it is a VT\_VARIANT. When you assign an external variable to a variant, the variant will also contain the same data as the original external variable.  
  
## Assigning Automation Variants to FieldRef Values  
 In [!INCLUDE[d365fin_md](../includes/d365fin_md.md)], if an Automation method returns a byte string \(bstr\) in a variant, you cannot assign that variant to a field that is a Code data type. Instead, you must first assign the variant to a code variable, and then assign the code variable to the FieldRef value. For example, the following code assigns a variant from an Automation method to a variable, and then assigns the variable to a field.  
  
```  
CodeVariable := AutomationMetodReturningBStrInVariant();  
FieldRef.Value := CodeVariable;  
```  
  
 In earlier versions of [!INCLUDE[d365fin_md](../includes/d365fin_md.md)], you could assign the variant to a Code FieldRef value.  
  
## See Also  
 [DATI2VARIANT method](../methods/devenv-DATI2VARIANT-method.md)   
 [ISACTION method \(Variant\)](../methods/devenv-ISACTION-method-Variant.md)   
 [ISAUTOMATION method \(Variant\)](../methods/devenv-ISAUTOMATION-method-Variant.md)   
 [ISBINARY method \(Variant\)](../methods/devenv-ISBINARY-method-Variant.md)   
 [ISBOOLEAN method \(Variant\)](../methods/devenv-ISBOOLEAN-method-Variant.md)   
 [ISCHAR method \(Variant\)](../methods/devenv-ISCHAR-method-Variant.md)   
 [ISCODE method \(Variant\)](../methods/devenv-ISCODE-method-Variant.md)   
 [ISCODEUNIT method \(Variant\)](../methods/devenv-ISCODEUNIT-method-Variant.md)   
 [ISDATE method \(Variant\)](../methods/devenv-ISDATE-method-Variant.md)   
 [ISDATEFORMULA method \(Variant\)](../methods/devenv-ISDATEFORMULA-method-Variant.md)   
 [ISDECIMAL method \(Variant\)](../methods/devenv-ISDECIMAL-method-Variant.md)   
 [ISFILE method \(Variant\)](../methods/devenv-ISFILE-method-Variant.md)   
 [ISINSTREAM method \(Variant\)](../methods/devenv-ISINSTREAM-method-Variant.md)   
 [ISINTEGER method \(Variant\)](../methods/devenv-ISINTEGER-method-Variant.md)   
 [ISOPTION method \(Variant\)](../methods/devenv-ISOPTION-method-Variant.md)   
 [ISOUTSTREAM method \(Variant\)](../methods/devenv-ISOUTSTREAM-method-Variant.md)   
 [ISRECORD method \(Variant\)](../methods/devenv-ISRECORD-method-Variant.md)   
 [ISTEXT method \(Variant\)](../methods/devenv-ISTEXT-method-Variant.md)   
 [ISTIME method \(Variant\)](../methods/devenv-ISTIME-method-Variant.md)   
 [ISTRANSACTIONTYPE method \(Variant\)](../methods/devenv-ISTRANSACTIONTYPE-method-Variant.md)   
 [VARIANT2DATE method](../methods/devenv-VARIANT2DATE-method.md)   
 [VARIANT2TIME method](../methods/devenv-VARIANT2TIME-method.md)
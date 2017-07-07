---
title: "SelectToken Method"
ms.author: solsen
ms.custom: na
ms.date: 06/29/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 620f0e32-eadc-43e9-8f6e-8fc0b12c3aaf
caps.latest.revision: 9
manager: edupont
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# SelectToken Method
Selects a JsonToken using a JPath expression.

```
[Ok := ] Value.SelectToken(Path, Result)
```

## Parameters
*Value*  
&emsp;Type: JsonToken

*Path*  
&emsp;Type: String  
&emsp;A valid JPath expression.

*Result*  
&emsp;Type: JsonToken  
&emsp;A **JsonToken** variable that will contain the result if the operation is successful.

## Property Value/Return Value
Type: Boolean

**True** if the operation was successful; otherwise, **false**.

If you omit this optional return value and if the select does not execute successfully, then a run-time error occurs.

## Remarks
The operation will fail if more or less than 1 tokens are the result of evaluating the JPath.

## Example
The following example shows how to select a value from a complex JSON object.
We build up a select expression in the *query* variable, we select the token corresponding to the salary of the employee with the given *employeeId*, and finally, we convert the token to a Decimal value.

We assume that the *company* token contains JSON data similar to the one below.

```
{ "company": {
    "employees": [
      { "id": "Marcy",
        "salary": 8.95
      },
      { "id": "John",
        "salary": 7
      },
      { "id": "Diana",
        "salary": 10.95
      }
    ]
  }
}
```

```
local procedure SelectEmployeeSalary(companyData : JsonToken; employeeId : Text) salary : Decimal;
var
    query : Text;
    salaryToken : JsonToken;
begin
    query := '$.company.employees[?(@.id=="'+employeeId+'")].salary';
    companyData.SelectToken(query, salaryToken);

    salary := salaryToken.AsValue().AsDecimal();    
end;

```
## See Also
[Getting Started](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)

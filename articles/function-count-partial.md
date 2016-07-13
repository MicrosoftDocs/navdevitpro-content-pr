<properties
                pageTitle="COUNT Function (Record) | Dynamics NAV"
                description="Describes the COUNT function that returns the number of records in a table."
                services=""
                documentationCenter=""
                authors="edupont04"/>
<tags
    ms.prod="dynamics-nav-2017"
    ms.topic="article"
    ms.devlang="na"
    ms.tgt_pltfrm="na"
    ms.workload="na"
    ms.date="07/13/2016"
    ms.author="edupont04" />

# COUNT Function (Record)
Counts the number of records in a table.
<!-- This topic represents changes to the topic for COUNT that is pending migration from CAPS -->
## Remarks
<!-- Change 1: SE bug 171777 for the CRM SDK returning a maximum of 5000 records -->

**IMPORTANT**:  If you use the COUNT function to return the number of records in a CRM integration table, a maximum count of 5000 is returned. The software development kit for Dynamics CRM does not include support for counting large entity collections. As a result, if a CRM integration table contains thousands of records, COUNT returns a maximum count of 5000.  

## See Also  

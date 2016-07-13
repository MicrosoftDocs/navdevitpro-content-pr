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
**IMPORTANT**:  If you use the COUNT function to return records from a CRM integration table, a maximum of 5000 records are returned. The software development kit for Dynamics CRM uses paging to handle large entity collections, and for performance reasons, Dynamics NAV gets the first page only.  

## See Also  

## Replacing OnBeforeCompanyOpen and OnAfterCompanyOpen ##

To improve the login time for a Dynamics 365 for Financials, extensions should no longer use the **OnBeforeCompanyOpen** and **OnAfterCompanyOpen** events. Following are some recommended patterns to use in place of these events.

- If the extension is subscribing to OnBefore(After)CompanyOpen in order to complete company setup for a newly created company, we  recommend subscribing to OnCompanyInitialize from codeunit2 instead
- If the extension is subscribing to OnBefore(After)CompanyOpen in order to perform some long-running data update, then either call the “update” when the extension gets called in code for the first time or apply the new task scheduler pattern for update 6 and later

*Task Scheduler Example:*
- TASKSCHEDULER.CREATETASK(CODEUNIT::"Job Queue User Handler",0,TRUE,COMPANYNAME,CURRENTDATETIME + 15000); // Add 15s
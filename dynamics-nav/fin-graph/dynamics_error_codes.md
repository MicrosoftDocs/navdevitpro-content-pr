---
title: Error Codes | Microsoft Docs
description: List of error codes.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/06/2017
ms.author: solsen
---

# Error Codes
The following table lists the error codes for ODataExceptions, NavCSideExceptions, NavNCLExceptions, and other exceptions. The default error code is "unknown".

|Exception Type |Error Message |Error Code|
|---------------|--------------|----------|
|**ODataExceptions**|||
|ODataArgumentException|An incompatible property definition already exists for Allowed_Companies_0.Name||
|ODataNotFoundException|Resource not found for the segment 'OfficeAppResourceRegistrations' multiple segment errors (Company, v1.0, nativeInvoicingSalesInvoices,metadata,nativeInvoicingItems , companies, company etc.)|`OData_Request_InvalidRequestUrl`, `OData_Request_badrequest`, `OData`, `OData_Request_InvalidGuidFormat`|
|ODataNotFoundException|Bad Request - Error in query syntax||
|ODataNotFoundException|Expression expected at position 153 in '(AAMkAGY2ZTQwODIwLTNkOWYtNDY3NC04N2JkLTE3MDEyNzlkM2VkOQBGAAAAAADFMnbflwH_RqlNoMYdjhvBBwCepO6AHq7GRJ13ldPngx5BAAAAAAEcAACepO6AHq7GRJ13ldPngx5BAAAGZyTmAAA=)'|
|ODataNotFoundException|'|' or ',' expected at position 3 in (GUID)||
|ODataInvalidOperationException|Control 'Last Date Modified' is read-only||
|ODataBadRequestException|Field 'taxable' must not be blank or empty. Could not validate the client concurrency token required by the service. Please provide a valid token in the client request.|`OData_Required_Param_NotProvided`, `OData_Invalid_Token`|
|ODataConflictException|Another user has already changed the record.|`OData_Entity_Changed`|
|**NavCSideExceptions**|||
|NavCSideDataException|There is no Cust. Ledger Entry within the filter.|`NavCSide_dataNotFound_Filter`|
|NavCSideRecordNotFoundException|The Acc. Sched. KPI Web srv. Setup does not exist. Identification fields and values: Primary Key=''|`NavCSide_Record_NotFound`|
|NavCSideValidateTableRelationException|The field Account No. of table Gen. Journal Line contains a value (ABL001) that cannot be found in the related table (Vendor).|`NavCSide_TableRelation_Invalidated`|
|NavCSideException|Cannot establish a connection to the SQL Server/Database. |`NavCSide_DB_Connection_Error`|
|NavCSideDuplicateKeyException|The Attachment Entity Buffer already exists. Identification fields and values: Document Id='{DAC3AB2F-5FEA-4AD2-A663-EF832F270A7B}',Id='{00000000-0000-0000-0000-000000000000}' |`NavCSide_Entity_With_Samekey`|
|**NavNCLExceptions**|||
|NavNCLDialogException|You cannot delete Item 1000 because there is at least one outstanding Sales Quote that includes this item. A customerNumber or a customerID must be provided. You may not enter numbers manually. If you want to enter numbers manually, please activate Manual Nos. in No. Series FA. You are not allowed to apply and post an entry to an entry with an earlier posting date. The"amount" should be a negative number.|
|NavNCLEvaluateException|The value "Depreciation" cannot be evaluated into type Option. ||
|NavNCLStringLengthExceededException|The length of the string is 57, but it must be less than or equal to 50 characters. Value: JACKSBORO PUMP & SPECIALTY BRIDGEPORT PUMP & SUPPLY, INC. |`NavNCL_String_ExceededLength`|
|NavNCLInvalidGuidFormatException|Invalid format of GUID string. The correct format of the GUID string is: CDEF7890-ABCD-0123-1234-567890ABCDEF where 0-9, A-F symbolizes hexadecimal digits. |`NavNCL_Invalid_GUID`|
|NavNCLCallbackNotAllowedException|Microsoft Sync 365 for fin Data services attempted to issue a client callback to shoe a confirmation dialog box. We found an item with the description |`NavNCL_Callback_NotAllowed`|
|**Other Exceptions**|||
|NavInvalidCredentialException|The server has rejected the client credentials |`Nav_InvalidCredentials`|
|NavTestFieldException|Balance must be equal to '0'  in G/L Account: No.=10100. Current value is '1,638.4'. Customer Posting Group must have a value in Customer: No.=C00690. It cannot be zero or empty.||
|NavCompanyNotFoundException|Cannot process the request because the default company cannot be found. You can specify a default company in the service configuration file, or specify one for each tenant, or you can add a query string in the form of "company=[name]". You can see the available companies by accessing the default OData web service, Company. For more information, see "OData Web Services" in Help. |`Nav_Company_NotFound`|
|NavFilterException|The filter "='SELLACRE24_W%2FOORINGS'" is not valid for the No. field on the Item table. The length of the string is 22, but it must be less than or equal to 20 characters. Value: SELLACRE24_W%2FOORINGS ||
|SecurityTokenExpiredException|The SAML2 token is not valid because its validity period has ended. |`SAML2_Token_Expired`|
|ArgumentNullException|Value cannot be null. Parameter name: azureAdUserTokenInfo ||
|FaultException|Sorry, but you can’t use this app with the user role that’s been assigned to you. Check with your admin and request access. If your company has Business Premium, this application will be made available to you soon.||
|NavTenantNotAccessibleException|The tenant 'msca1a7355t05263373' is not accessible ||
|NavSqlDatabaseSyncException|Metadata is not in sync for table with ID 2000000073. Please try again later or contact your system administrator.||

## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](resources/dynamics_overview.md) 

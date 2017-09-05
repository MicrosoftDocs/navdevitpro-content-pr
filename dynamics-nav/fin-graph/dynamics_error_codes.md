---
title: Error Codes | Microsoft Docs
description: A list of error codes.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/05/2017
ms.author: solsen
---

# Error Codes
The following table contains a list of error codes for various exceptions. The default error code is "Unknown".

|Error Code                    |Exception Class|Error Message|
|------------------------------|---------------|-------------|
|`BadRequest_InvalidRequestUrl`|ODataArgumentException|An incompatible property definition already exists for `Allowed_Companies_0.Name`|
|`BadRequest_NotFound`|ODataNotFoundException|Resource not found for the segment 'OfficeAppResourceRegistrations' multiple segment errors (Company, v1.0, nativeInvoicingSalesInvoices,metadata,nativeInvoicingItems , companies, company etc.) Bad Request - Error in query syntax Expression expected at position 153 in `AAMkAGY2ZTQwODIwLTNkOWYtNDY3NC04N2JkLTE3MDEyNzlkM2VkOQBGAAAAAADFMnbflwH_RqlNoMYdjhvBBwCepO6AHq7GRJ13ldPngx5BAAAAAAEcAACepO6AHq7GRJ13ldPngx5BAAAGZyTmAAA=)` `|` or `,` expected at position 3 in (GUID)|
|`BadRequest_InvalidOperation`|ODataInvalidOperationException|Control 'Last Date Modified' is read-only|
|`BadRequest_RequiredParamNotProvided`|ODataBadRequestException|Field 'taxable' must not be blank or empty.|
|`BadRequest_InvalidToken`|ODataBadRequestException|Could not validate the client concurrency token required by the service. Please provide a valid token in the client request.|
|`Request_EntityChanged`|ODataConflictException|Another user has already changed the record.|
|`Internal_dataNotFoundFilter`|NavCSideDataException|There is no Cust. Ledger Entry within the filter.|
|`Internal_RecordNotFound`|NavCSideRecordNotFoundException|The Acc. Sched. KPI Web srv. Setup does not exist. Identification fields and values: Primary Key=''|
|`Internal_InvalidTableRelation`|NavCSideValidateTableRelationException|The field Account No. of table Gen. Journal Line contains a value (ABL001) that cannot be found in the related table (Vendor).|
|`Internal_ServerError`|NavCSideException|Cannot establish a connection to the SQL Server/Database.|
|`Internal_EntityWithSameKeyExists`|NavCSideDuplicateKeyException|The Attachment Entity Buffer already exists. Identification fields and values: Document Id='{DAC3AB2F-5FEA-4AD2-A663-EF832F270A7B}',Id='{00000000-0000-0000-0000-000000000000}`|
|`Application_DialogException`|NavNCLDialogException|You cannot delete Item 1000 because there is at least one outstanding Sales Quote that includes this item. A customerNumber or a customerID must be provided. You may not enter numbers manually. If you want to enter numbers manually, please activate Manual Nos. in No. Series FA. You are not allowed to apply and post an entry to an entry with an earlier posting date. The"amount" should be a negative number.|
|`Application_EvaluateException`|NavNCLEvaluateException|The value "Depreciation" can't be evaluated into type Option.|
|`Application_StringExceededLength`|NavNCLStringLengthExceededException|The length of the string is 57, but it must be less than or equal to 50 characters. Value: JACKSBORO PUMP & SPECIALTY BRIDGEPORT PUMP & SUPPLY, INC.|
|`Application_Invalid_GUID`|NavNCLInvalidGuidFormatException|Invalid format of GUID string. The correct format of the GUID string is: CDEF7890-ABCD-0123-1234-567890ABCDEF where 0-9, A-F symbolizes hexadecimal digits.|
|`Application_CallbackNotAllowed`|NavNCLCallbackNotAllowedException|Microsoft Sync 365 for fin Data services attempted to issue a client callback to show a confirmation dialog box. We found an item with the description.||
`Authenciation_InvalidCredentials`|NavInvalidCredentialException|The server has rejected the client credentials|
|`Application_FieldValidationException`|NavTestFieldException|Balance must be equal to '0' in G/L Account: No.=10100. Current value is '1,638.4'. Customer Posting Group must have a value in Customer: No.=C00690. It cannot be zero or empty.|
|`Internal_CompanyNotFound`|NavCompanyNotFoundException|Cannot process the request because the default company cannot be found. You can specify a default company in the service configuration file, or specify one for each tenant, or you can add a query string in the form of "company=[name]". You can see the available companies by accessing the default OData web service, Company. For more information, see "OData Web Services" in Help.|
|`Application_StringExceededLength`|NavFilterException|The filter `"='SELLACRE24_W%2FOORINGS'"` is not valid for the No. field on the Item table. The length of the string is 22, but it must be less than or equal to 20 characters. Value: SELLACRE24_W%2FOORINGS|
|`Authentication_TokenExpired`|SecurityTokenExpiredException|The SAML2 token is not valid because its validity period has ended.|
|`Authentication_MissingOrMalformedToken`|ArgumentNullException|Value cannot be null. Parameter name: azureAdUserTokenInfo|
|`Authorization_InsufficientPermissions`|FaultException|Sorry, but you can’t use this app with the user role that’s been assigned to you. Check with your admin and request access. If your company has Business Premium, this application will be made available to you soon.|
|`Internal_TenantUnavailable`|NavTenantNotAccessibleException|The tenant 'msca1a7355t05263373' is not accessible|
|`Internal_MetadataSyncError`|NavSqlDatabaseSyncException|Metadata is not in sync for table with ID 2000000073. Please try again later or contact your system administrator.|








## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 

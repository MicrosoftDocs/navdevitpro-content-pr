---
title: "Updated Code for Table 5330 CRM Connection Setup"
ms.custom: na
ms.date: 20/03/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 6ea75b39-cf7d-4c88-868b-86fa0be2426b
caps.latest.revision: 4
author: jswymer
---
## Updated Code for Table 5330 CRM Connection Setup

The following code is replacement code for Table **5330 CRM Connection Setup** after converting a [!INCLUDE[navcorfu](includes/navcorfu_md.md)] database to [!INCLUDE[nav2017](includes/nav2017.md)]. Copy the code to a text editor, save as a .txt file type, and then import the file to the database by using the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)].

```
OBJECT Table 5330 CRM Connection Setup
{
  OBJECT-PROPERTIES
  {
    Date=;
    Time=;
    Version List=;
  }
  PROPERTIES
  {
    Permissions=TableData 1261=rimd;
  }
  FIELDS
  {
    { 1   ;   ;Primary Key         ;Code20         }
    { 2   ;   ;Server Address      ;Text250       ;CaptionML=ENU=Dynamics CRM URL }
    { 3   ;   ;User Name           ;Text250        }
    { 4   ;   ;User Password Key   ;GUID           }
    { 60  ;   ;Is Enabled          ;Boolean        }
    { 61  ;   ;Is User Mapping Required;Boolean   ;InitValue=Yes;
                                                   CaptionML=ENU=Dynamics NAV Users Must Map to Dynamics CRM Users }
  }
  KEYS
  {
    {    ;Primary Key                             ;Clustered=Yes }
  }
  FIELDGROUPS
  {
  }
  CODE
  {
    VAR
      ConnectionStringFormatTok@1000 : TextConst '@@@={Locked};ENU="Url=%1; UserName=%2; Password=%3"';
      CantRegisterDisabledConnectionErr@1001 : TextConst 'ENU=A disabled connection cannot be registered.';
      ConnectionWithCallerIdStringFormatTok@1002 : TextConst '@@@={Locked};ENU="Url=%1; UserName=%2; Password=%3; CallerID=%4"';
      UnableToRetrieveCrmVersionErr@1004 : TextConst 'ENU=Unable to retrieve Dynamics CRM version.';
      MissingUsernameTok@1003 : TextConst '@@@={Locked};ENU={USER}';
      MissingPasswordTok@1005 : TextConst '@@@={Locked};ENU={PASSWORD}';

    PROCEDURE HasPassword@8() : Boolean;
    BEGIN
      EXIT(GetPassword <> '');
    END;

    PROCEDURE SetPassword@1(PasswordText@1000 : Text);
    VAR
      ServicePassword@1002 : Record 1261;
    BEGIN
      IF ISNULLGUID("User Password Key") OR NOT ServicePassword.GET("User Password Key") THEN BEGIN
        ServicePassword.SavePassword(PasswordText);
        ServicePassword.INSERT(TRUE);
        "User Password Key" := ServicePassword.Key;
      END ELSE BEGIN
        ServicePassword.SavePassword(PasswordText);
        ServicePassword.MODIFY;
      END;
    END;

    PROCEDURE UpdateAllConnectionRegistrations@4();
    VAR
      CRMConnectionSetup@1000 : Record 5330;
    BEGIN
      UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::CRM,GETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::CRM));
      IF CRMConnectionSetup.FINDSET THEN
        REPEAT
          CRMConnectionSetup.UnregisterConnection;
          IF CRMConnectionSetup."Is Enabled" THEN
            CRMConnectionSetup.RegisterUserConnection;
        UNTIL CRMConnectionSetup.NEXT = 0;
    END;

    PROCEDURE RegisterConnection@17();
    BEGIN
      RegisterConnectionWithName("Primary Key");
    END;

    PROCEDURE RegisterConnectionWithName@12(ConnectionName@1000 : Text);
    BEGIN
      REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::CRM,ConnectionName,ConstructConnectionString);
      IF ConnectionName = '' THEN
        SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::CRM,ConnectionName);
    END;

    PROCEDURE UnregisterConnection@5() : Boolean;
    BEGIN
      EXIT(UnregisterConnectionWithName("Primary Key"));
    END;

    [TryFunction]
    PROCEDURE UnregisterConnectionWithName@20(ConnectionName@1000 : Text);
    BEGIN
      UNREGISTERTABLECONNECTION(TABLECONNECTIONTYPE::CRM,ConnectionName);
    END;

    PROCEDURE ConstructConnectionString@3() : Text;
    BEGIN
      IF "User Name" = '' THEN
        EXIT(STRSUBSTNO(ConnectionStringFormatTok,"Server Address",MissingUsernameTok,MissingPasswordTok));

      EXIT(STRSUBSTNO(ConnectionStringFormatTok,"Server Address","User Name",GetPassword));
    END;

    LOCAL PROCEDURE ConstructConnectionStringWithCalledID@16(CallerID@1000 : Text) : Text;
    BEGIN
      EXIT(STRSUBSTNO(ConnectionWithCallerIdStringFormatTok,"Server Address","User Name",GetPassword,CallerID));
    END;

    PROCEDURE RegisterUserConnection@6();
    VAR
      User@1002 : Record 2000000120;
      CallerID@1001 : GUID;
    BEGIN
      RegisterConnection;

      IF NOT User.GET(DATABASE.USERSECURITYID) THEN
        EXIT;

      IF User."Authentication Email" <> '' THEN BEGIN
        IF NOT TryGetSystemUserIdFromEmail(User."Authentication Email",CallerID) THEN
          CLEARLASTERROR;
      END;

      IF NOT ISNULLGUID(CallerID) THEN BEGIN
        UnregisterConnection;
        RegisterConnectionWithCallerID(CallerID);
      END ELSE BEGIN
        IF "Is User Mapping Required" THEN
          UnregisterConnection;
      END;
    END;

    LOCAL PROCEDURE RegisterConnectionWithCallerID@11(CallerID@1000 : Text);
    BEGIN
      IF NOT "Is Enabled" THEN
        ERROR(CantRegisterDisabledConnectionErr);

      REGISTERTABLECONNECTION(TABLECONNECTIONTYPE::CRM,"Primary Key",ConstructConnectionStringWithCalledID(CallerID));
      IF "Primary Key" = '' THEN
        SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::CRM,"Primary Key");
    END;

    PROCEDURE GetIntegrationUserID@7() : GUID;
    VAR
      CRMConnectionSetup@1000 : Record 5330;
      CRMSystemuser@1001 : Record 5340;
    BEGIN
      CRMConnectionSetup.SETRANGE("Is Enabled",TRUE);
      CRMConnectionSetup.FINDFIRST;
      CRMSystemuser.SETRANGE(InternalEMailAddress,CRMConnectionSetup."User Name");
      IF CRMSystemuser.FINDFIRST THEN
        EXIT(CRMSystemuser.SystemUserId);
    END;

    LOCAL PROCEDURE GetPassword@2() : Text;
    VAR
      ServicePassword@1000 : Record 1261;
    BEGIN
      IF NOT ISNULLGUID("User Password Key") THEN
        IF ServicePassword.GET("User Password Key") THEN
          EXIT(ServicePassword.GetPassword);
    END;

    PROCEDURE TestConnection@9() Success : Boolean;
    VAR
      TestConnectionName@1000 : Text;
    BEGIN
      TestConnectionName := FORMAT(CREATEGUID);
      UnregisterConnectionWithName(TestConnectionName);
      RegisterConnectionWithName(TestConnectionName);
      SETDEFAULTTABLECONNECTION(TABLECONNECTIONTYPE::CRM,TestConnectionName,TRUE);
      IF TryReadSystemUsers THEN
        Success := TRUE;
      UnregisterConnectionWithName(TestConnectionName);
    END;

    [TryFunction]
    LOCAL PROCEDURE TryReadSystemUsers@14();
    VAR
      CRMSystemuser@1000 : Record 5340;
    BEGIN
      IF CRMSystemuser.FINDFIRST THEN;
    END;

    LOCAL PROCEDURE CreateOrganizationService@10(VAR service@1000 : DotNet "'Microsoft.Xrm.Sdk, Version=8.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'.Microsoft.Xrm.Sdk.IOrganizationService");
    VAR
      crmConnection@1002 : DotNet "'Microsoft.Xrm.Tooling.Connector, Version=2.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'.Microsoft.Xrm.Tooling.Connector.CrmServiceClient";
    BEGIN
      crmConnection := crmConnection.CrmServiceClient(ConstructConnectionString);
      IF crmConnection.IsReady THEN BEGIN
        IF NOT ISNULL(crmConnection.OrganizationWebProxyClient) THEN
          service := crmConnection.OrganizationWebProxyClient
        ELSE
          service := crmConnection.OrganizationServiceProxy;
        EXIT;
      END;

      IF NOT ISNULL(crmConnection.LastCrmException) THEN
        ERROR(crmConnection.LastCrmException.Message);
      ERROR(crmConnection.LastCrmError);
    END;

    [TryFunction]
    PROCEDURE GetCrmVersion@15(VAR Version@1003 : Text);
    VAR
      service@1000 : DotNet "'Microsoft.Xrm.Sdk, Version=8.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'.Microsoft.Xrm.Sdk.IOrganizationService";
      request@1001 : DotNet "'Microsoft.Xrm.Sdk, Version=8.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'.Microsoft.Xrm.Sdk.OrganizationRequest";
      response@1002 : DotNet "'Microsoft.Xrm.Sdk, Version=8.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'.Microsoft.Xrm.Sdk.OrganizationResponse";
    BEGIN
      Version := '';
      IF STRPOS("Server Address",'@@') = 1 THEN
        EXIT;
      CreateOrganizationService(service);
      request := request.OrganizationRequest;
      request.RequestName := 'RetrieveVersion';
      response := service.Execute(request);
      IF NOT response.Results.TryGetValue('Version',Version) THEN
        ERROR(UnableToRetrieveCrmVersionErr);
    END;

    PROCEDURE IsCurrentUserMappedToCrmSystemUser@13() : Boolean;
    VAR
      User@1000 : Record 2000000120;
      CRMSystemUserId@1002 : GUID;
    BEGIN
      IF NOT User.GET(DATABASE.USERSECURITYID) THEN
        EXIT(FALSE);

      IF User."Authentication Email" = '' THEN
        EXIT(FALSE);

      EXIT(TryGetSystemUserIdFromEmail(User."Authentication Email",CRMSystemUserId));
    END;

    [TryFunction]
    LOCAL PROCEDURE TryGetSystemUserIdFromEmail@18(EmailAddress@1000 : Text;VAR SystemUserId@1001 : GUID);
    VAR
      CRMSystemuser@1002 : Record 5340;
    BEGIN
      CRMSystemuser.SETRANGE(InternalEMailAddress,EmailAddress);
      CRMSystemuser.FINDFIRST;
      SystemUserId := CRMSystemuser.SystemUserId;
    END;

    BEGIN
    END.
  }
}

```

## See Also  
 [Converting a Database](Converting-a-Database.md)  
 [How to: Import-Objects](How-to--Import-Objects.md)

---
external help file: Microsoft.Dynamics.Nav.Model.Tools.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=524402
schema: 2.0.0
---

# New-NAVCrmTable

## SYNOPSIS
Creates Microsoft Dynamics NAV table objects that are based on Microsoft Dynamics CRM entities.
The table objects are saved as .txt files.

## SYNTAX

### NormalParameters
```
New-NAVCrmTable [-CRMServer] <Uri> [-Credential] <PSCredential> [-EntityLogicalName] <string[]> [-ObjectId] <int[]> [-AuthenticationType <CrmAuthentication> {AD | IFD | Office365 | OAuth}] [-ClientId <string>]
[-Domain <string>] [-Force <SwitchParameter>] [-HomeRealmUri <string>] [-Name <string[]>] [-OutputPath <string>] [-RedirectUri <string>] [<CommonParameters>]
```
### PassThroughConnectionString
```
New-NAVCrmTable [-EntityLogicalName] <string[]> [-ObjectId] <int[]>
-ConnectionString <string> [-Force <SwitchParameter>] [-Name <string[]>] [-OutputPath <string>] [<CommonParameters>]
```
## DESCRIPTION
Use this cmdlet when integrating Dynamics NAV with Dynamics CRM.
This cmdlet creates one or more table objects in Dynamics NAV that correspond to entities in Dynamics CRM.
The created tables are eventually used to map fields in Dynamics CRM with fields in business data tables of Dynamics NAV.
Each table object is saved as a .txt file on your computer or network and can be imported into a Dynamics NAV  database.
The tables have the following characteristics:

- The TableType property is set to CRM.
- Contains field definitions for all fields in a Dynamics CRM entity that have a data type that is supported by Dynamics NAV. References to other Dynamics CRM entities will only be included if the entity is included in the command line.

Only external tables that are based on by actual Dynamics CRM entities are supported. In Dynamics CRM, the entities must support one or more of the following actions:
-   Create
-   Update
-   Delete
-   Retrieve
-   RetrieveMultiple
-   Associate (one-to-many relationship only)
-   Disassociate (one-to-many relationship only)
-   Execute (only for setting state)

## EXAMPLES

### EXAMPLE 1
```
New-NavCrmTable -CRMServer myserver.crm.dynamics.com -Credential (Get-Credential -UserName user@myserver.onmicrosoft.com -Message "Enter Password") -EntityLogicalName account -Name "CRM Account" -ObjectId 50500 -OutputPath c:\CrmObjects
          FileName    : c:\CrmObjects\TAB50500.TXT
          ObjectType  : Table
          Id          : 50500
          VersionList :
          Date        :
          Time        :
          Modified    : False
```

This example creates a single Dynamics NAV table object based on the account entity in Dynamics CRM.
The created table has the ID 50500 and name CRM Account.

### EXAMPLE 2
```
New-NavCrmTable -CRMServer myserver.crm.dynamics.com -Credential (Get-Credential -UserName user@myserver.onmicrosoft.com -Message "Enter Password") -Entity account,contact -Name "CRM Account","CRM Contact" -ObjectId 50500,50501 -OutputPath c:\CrmObjects
          FileName    : C:\CrmObjects\TAB50500.TXT
          ObjectType  : Table
          Id          : 50500
          VersionList :
          Date        :
          Time        :
          Modified    : False
          FileName    : C:\CrmObjects\TAB50501.TXT
          ObjectType  : Table
          Id          : 50501
          VersionList :
          Date        :
          Time        :
          Modified    : False
```

This example creates two Dynamics NAV table objects based on the account and contact entities in Dynamics CRM.

### EXAMPLE 3
```
New-NavCrmTable -CRMServer https://myserver.local.com/myOrg -Credential (Get-Credential -UserName myserver\UserName -Message "Enter Password")  -AuthenticationType=AD -Entity account,contact -Name "CRM Account","CRM Contact" -ObjectId 50500,50501 -OutputPath c:\CrmObjects
```
This example creates two Dynamics NAV table objects based on the account and contact entities in on-premise Dynamics CRM installation using an  with Azure AD authentication.

### EXAMPLE 4
```
New-NavCrmTable -CRMServer . -Credential (Get-Credential -UserName "." -Password ".") -ConnectionString "Url=http://myserver.net/org;UserName=myServer\MyUser;Password=myPassword;AuthType=AD" -Entity account,conta -Name "CRM Account","CRM Contact" -ObjectId 50500,50501 -OutputPath c:\CrmObjects

```
This example creates two Dynamics NAV table objects based on the account and contact entities in Dynamics CRM using a user specified custom connection string.

## PARAMETERS

### -AuthenticationType
Specifies the authentication type to connect to Dynamics CRM instance.
-   OAuth is supported for online and on-premises instances.
-   AD and IFD (AD FS enabled) are supported for on-premises instances only.
-   Office365 is permitted for online instances only.

The AuthenticationType parameter is optional. For a list of valid
values, see [AuthenticationType Enumeration](https://aka.ms/dynamicscrmauthenticationtypeenumeration).
The default value is Office365, which is the required authentication
type for CRM Online.

Possible values: AD, IFD, Office365, OAuth

```yaml
Type: Enumeration
Parameter Sets: NormalParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CRMServer
Specifies the URl of the Dynamics CRM server to connect to.
The Dynamics CRM server provides access to the entity that you want to create as a table in Dynamics NAV.
The URL specifies the URI scheme, such as HTTPS or HTTP, and the fully qualified domain name (FQDN) that identifies the Dynamics CRM organization and the computer where the Dynamics CRM server is installed.
For connecting to Dynamics CRM Online, the format is typically scheme://organizationname.domainname, such as https://mycrm.crm4.dynamics.com, where https is the scheme, myorganization is the organization and crm4.dynamics.com is the domain.

```yaml
Type: Uri
Parameter Sets: NormalParameters
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user name and password for accessing Dynamics CRM.

```yaml
Type: PSCredential
Parameter Sets: NormalParameters
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntityLogicalName
Specifies the logical names of the Dynamics CRM entities for which to create a Dynamics NAV table.
This parameter is a comma-separated list.
So when you are creating tables for multiple entities, separate each entity logical name with a comma.
Each entity logical name must have a corresponding value in the ObjectID parameter based on its position is the list.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Specifies that existing files of the same name in the OutputPath folder are to be overwritten.
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the names of the new tables to be created.
This parameter is a comma-separated list.
So when creating multiple tables, separate each table name by a comma.
Each individual name must have a corresponding item in the ObjectID and the EntityLogicalName parameters, based on its position in the list.

The Name parameter is optional, but if you use it, you must specify the names of all new tables, not just one.
If you do not specify names, then the tables get the entity logical names as specified by the EntityLogicalName parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectUri
Specifies the Redirect URI that was assigned to the Dynamics NAV    application when it was registered in Microsoft Azure Active Directory    or Active Directory Federation Services (AD FS). This parameter is    only applicable when the -AuthenticationType parameter is set to OAuth.

```yaml
Type: String[]
Parameter Sets: NormalParameters
Aliases:

Required: False
Position: Named
Default value:
Accept pipeline input: False
Accept wildcard characters:  False
```

### -Domain
Specifies the domain that will verify user credentials.

```yaml
Type: String[]
Parameter Sets: NormalParameters
Aliases:

Required: False
Position: Named
Default value:
Accept pipeline input: False
Accept wildcard characters:  False
```

### -HomeRealmUri
Specifies the Home Realm Uri. This parameter is only applicable when
the -AuthenticationType parameter is set to OAuth.

```yaml
Type: String[]
Parameter Sets: NormalParameters
Aliases:

Required: False
Position: Named
Default value:
Accept pipeline input: False
Accept wildcard characters:  False
```

### -ClientId
Specifies the Client ID (or Application ID) that was assigned to the Dynamics NAV application when it was registered in Microsoft Azure Active Directory or Active Directory Federation Services (AD FS). This parameter is only applicable when the -AuthenticationType parameter is set to OAuth.

```yaml
Type: String[]
Parameter Sets: NormalParameters
Aliases:

Required: False
Position: Named
Default value:
Accept pipeline input: False
Accept wildcard characters:  False
```

### -ObjectId
Specifies the IDs of the table objects to be created.
This parameter is a comma-separated list.
So when you are creating multiple table objects, separate each ID with a comma.
Each ID must have a corresponding value in the EntityLogicalName parameter, and optionally in the Name parameter, based on its position is the list.

```yaml
Type: Int32[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputPath
Specifies the folder path to where the generated .txt files for tables will be saved, such as "c:\CRMObjects".
If the folder path does not already exist, it will be created.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionString
Specifies a passthrough connection string that will be used to connect
to the Dynamics CRM instance.

For information about how to create a valid connection string, see
[Use connection strings in XRM tooling to connect to Dynamics 365](https://go.microsoft.com/fwlink/?linkid=848464).

```yaml
Type: String[]
Parameter Sets: PassThroughConnectionString
Aliases:

Required: False
Position: Named
Default value:
Accept pipeline input: False
Accept wildcard characters:  False

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

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

```
New-NAVCrmTable [-CRMServer] <Uri> [-Credential] <PSCredential> [-EntityLogicalName] <String[]>
 [-ObjectId] <Int32[]> [-Name <String[]>] [-AuthenticationType <String>] [-OutputPath <String>] [-Force]
 [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use this cmdlet when integrating Microsoft Dynamics NAV with Microsoft Dynamics CRM.
This cmdlet creates one or more table objects in Microsoft Dynamics NAV that correspond to entities in Microsoft Dynamics CRM.
The created tables are eventually used to map fields in Microsoft Dynamics CRM with fields in business data tables of Microsoft Dynamics NAV.
Each table object is saved as a .txt file on your computer or network and can be imported into a Microsoft Dynamics NAV  database.
The tables have the following characteristics:

- The TableType property is set to CRM.
- Contains field definitions for all fields in a Microsoft Dynamics CRM entity that have a data type that is supported by Microsoft Dynamics NAV. References to other Microsoft Dynamics CRM entities will only be included if the entity is included in the command line.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-NavCrmTable -Server myserver.crm.dynamics.com -Credential (Get-Credential -UserName user@myserver.onmicrosoft.com -Message "Enter Password") -EntityLogicalName account -Name "CRM Account" -ObjectId 50500 -OutputPath c:\CrmObjects
          FileName    : c:\CrmObjects\TAB50500.TXT
          ObjectType  : Table
          Id          : 50500
          VersionList :
          Date        :
          Time        :
          Modified    : False
```

Description

-----------

This example creates a single Microsoft Dynamics NAV table object based on the account entity in Microsoft Dynamics CRM.
The created table has the ID 50500 and name CRM Account.

### EXAMPLE 2
```
PS C:\>New-NavCrmTable -Server myserver.crm.dynamics.com -Credential (Get-Credential -UserName user@myserver.onmicrosoft.com -Message "Enter Password") -Entity account,contact -Name "CRM Account","CRM Contact" -ObjectId 50500,50501 -OutputPath c:\CrmObjects
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

This example creates two Microsoft Dynamics NAV table objects based on the account and contact entities in Microsoft Dynamics CRM.

## PARAMETERS

### -Credential
Specifies a user name and password for accessing Microsoft Dynamics CRM.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CRMServer
Specifies the URl of the Microsoft Dynamics CRM server to connect to.
The Microsoft Dynamics CRM server provides access to the entity that you want to create as a table in Microsoft Dynamics NAV.
The URL specifies the URI scheme, such as HTTPS or HTTP, and the fully qualified domain name (FQDN) that identifies the Microsoft Dynamics CRM organization and the computer where the Microsoft Dynamics CRM server is installed.
For connecting to Microsoft Dynamics CRM Online, the format is typically scheme://organizationname.domainname, such as https://mycrm.crm4.dynamics.com, where https is the scheme, myorganization is the organization and crm4.dynamics.com is the domain.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntityLogicalName
Specifies the logical names of the Microsoft Dynamics CRM entities for which to create a Microsoft Dynamics NAV table.
This parameter is a comma-separated list.
So when you are creating tables for multiple entities, separate each entity logical name with a comma.
Each entity logical name must have a corresponding value in the ObjectID parameter based on its position is the list.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
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
Position: 5
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

### -AuthenticationType
{{Fill AuthenticationType Description}}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

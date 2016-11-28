---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Rename-NAVCompany

## SYNOPSIS
Renames a company in a Microsoft Dynamics NAV database.

## SYNTAX

```
Rename-NAVCompany [-Tenant <TenantId>] [-CompanyName] <String> [-NewCompanyName] <String>
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Rename-NAVCompany cmdlet to rename a company in a Microsoft Dynamics NAV database.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Rename-NAVCompany -ServerInstance 'DynamicsNAV' -CompanyName 'CRONUS International Ltd.' -NewCompanyName 'MyCompany' -Verbose

VERBOSE: NavCommand.BeginProcessing
VERBOSE: NavCommand.ProcessRecord
VERBOSE: Renaming company 'CRONUS International Ltd.' to 'MyCompany' ... 

VERBOSE: Renaming of company 'CRONUS International Ltd.' to 'MyCompany' has completed successfully. 
VERBOSE: NavCommand.EndProcessing
```

Description

-----------

This example renames the CRONUS International Ltd.
in the CRONUS database to MyCompany.

### -------------------------- EXAMPLE 2 --------------------------
```
Rename-NAVCompany -ServerInstance 'DynamicsNAV' -CompanyName 'CRONUS International Ltd.' -NewCompanyName 'MyCompany' -ErrorLogFileName C:\NavDatabases\ErrorLog.txt
```

Description

-----------

This example renames the company CRONUS International Ltd.
in the CRONUS database to MyCompany.
Errors are logged to the file C:\NavDatabases\ErrorLog.txt.

## PARAMETERS

### -CompanyName
Specifies the name of the company that you want to rename.
This must be an existing company in the specified Microsoft Dynamics NAV database.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewCompanyName
Specifies the new name of the company.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Tenant
Specifies the ID of the tenant that the company is stored in, such as Tenant1.
This parameter is required unless the specified service instance is not configured to run multiple tenants.

```yaml
Type: TenantId
Parameter Sets: (All)
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Describes what would happen if you executed the command without actually executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
{{Fill Force Description}}

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

## INPUTS

## OUTPUTS

## NOTES
## RELATED LINKS


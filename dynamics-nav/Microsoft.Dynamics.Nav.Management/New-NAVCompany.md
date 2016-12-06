---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401373
schema: 2.0.0
---

# New-NAVCompany

## SYNOPSIS
Creates a new Microsoft Dynamics NAV company in the specified database.

## SYNTAX

```
New-NAVCompany [-Tenant <TenantId>] [-CompanyName] <String> [-EvaluationCompany] [-ServerInstance] <String>
 [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the New-NAVCompany cmdlet to create a new company in a Microsoft Dynamics NAV database.
The company that the New-NAVCompany cmdlet creates is empty.
To create a company that includes the data from an existing company, use the Copy-NAVCompany cmdlet.

## EXAMPLES

### EXAMPLE 1
```
New-NAVCompany -ServerInstance DynamicsNAV -Tenant CRONUS -CompanyName 'CRONUS Subsidiary'
```

This example creates the company CRONUS Subsidiary in the CRONUS tenant database, which is mounted against the DynamicsNAV server instance.

## PARAMETERS

### -CompanyName
Specifies the name of the company that you want to create.
If a company with that name already exists in the Microsoft Dynamics NAV database, the cmdlet fails.

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

### -EvaluationCompany
Specifies whether the company that you want to create is an evaluation company.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
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
Specifies the ID of the tenant that the company must be created in, such as Tenant1.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
## RELATED LINKS

[Copy-NAVCompany](Copy-NAVCompany.md)

[Get-NAVCompany](Get-NAVCompany.md)

[Remove-NAVCompany](Remove-NAVCompany.md)

[Rename-NAVCompany](Rename-NAVCompany.md)

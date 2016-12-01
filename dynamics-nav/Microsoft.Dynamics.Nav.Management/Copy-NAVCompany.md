---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Copy-NAVCompany

## SYNOPSIS
Creates a new company and copies all data from an existing company in the same tenant database.

## SYNTAX

```
Copy-NAVCompany [-Tenant <TenantId>] [-DestinationCompanyName] <String> [-SourceCompanyName] <String>
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Copy-NAVCompany cmdlet to create a new company based on an existing company in the same tenant database.
The company that the Copy-NAVCompany cmdlet creates includes the data from the existing company.
To create an empty company, use the New-NAVCompany cmdlet.

## EXAMPLES

### EXAMPLE 1
```
Copy-NAVCompany -ServerInstance DynamicsNAV -Tenant CRONUS -DestinationCompanyName 'Cronus Subsidiary' -SourceCompanyName 'Cronus International Ltd.'
```
This example creates a copy of the Cronus International Ltd.
company in the database that has the tenant ID CRONUS and which is mounted against the DynamicsNAV server instance.

## PARAMETERS

### -DestinationCompanyName
Specifies the name of the company that you want to create.
If a company with that name already exists in the Microsoft Dynamics NAV database, the cmdlet fails.

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

### -SourceCompanyName
Specifies the name of the company that you want to copy.

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

## INPUTS

## OUTPUTS

## NOTES
## RELATED LINKS
[Get-NAVCompany](Get-NAVCompany.md)  

[New-NAVCompany](New-NAVCompany.md)  

[Remove-NAVCompany](Get-NAVCompany.md)

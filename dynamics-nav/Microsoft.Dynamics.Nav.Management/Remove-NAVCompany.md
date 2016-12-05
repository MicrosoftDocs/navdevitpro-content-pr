---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Remove-NAVCompany

## SYNOPSIS
Removes a company from a Microsoft Dynamics NAV database.

## SYNTAX

```
Remove-NAVCompany [-Tenant <TenantId>] [-CompanyName] <String> [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm]
```

## DESCRIPTION
Use the Remove-NAVCompany cmdlet to remove a company from the specified tenant database.
When you remove a company, the company and all of the data that it contains will be deleted.
We recommend that you make a backup before you remove a company.
You must also make sure that you are the only active user for the company before you remove the company.

## EXAMPLES

### EXAMPLE 1
```
Remove-NAVCompany -ServerInstance DynamicsNAV -Tenant CRONUS -CompanyName 'CRONUS International Ltd.'
```

This example removes the CRONUS International Ltd.
company from the database that has the tenant ID CRONUS and which is mounted against the DynamicsNAV server instance.

## PARAMETERS

### -CompanyName
Specifies the name of the company that you want to delete.
If the company does not exist in the Microsoft Dynamics NAV database, the operation fails.

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
[Copy-NAVCompany](Copy-NAVCompany.md)  

[Get-NAVCompany](Get-NAVCompany.md)  

[New-NAVCompany](New-NAVCompany.md)

[Rename-NAVCompany](Rename-NAVCompany.md)  

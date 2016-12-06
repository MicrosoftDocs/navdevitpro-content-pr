---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=403853
schema: 2.0.0
---

# Stop-NAVDataUpgrade

## SYNOPSIS
Stops the data upgrade process that is currently running or suspended.

## SYNTAX

```
Stop-NAVDataUpgrade [[-Tenant] <TenantId>] [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
You cannot resume a data upgrade process after you have run the Stop-NavDataUpgrade cmdlet.
Stop-NavDataUpgrade cmdlet will rollback changes that were made by upgrade function that were not completed. Changes made by completed upgrade functions will not be rolled back.

## EXAMPLES

### EXAMPLE 1
```
Stop-NAVDataUpgrade -ServerInstance DynamicsNAV -Force
```

This example stops the currently running data upgrade process.

## PARAMETERS

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.
You must include the name within single quotation marks.

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
Specifies the ID of the tenant that you want to synchronize with the application, such as Tenant1. This parameter is required unless the specified service instance is not configured to run multiple tenants.

```yaml
Type: TenantId
Parameter Sets: (All)
Aliases: Id

Required: False
Position: 2
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

### System.String
You can pass the value of the ServerInstance and Tenant parameters as a string to this cmdlet.

## OUTPUTS

## NOTES
## RELATED LINKS

[Get-NAVDataUpgrade](Get-NAVDataUpgrade.md)

[Resume-NAVDataUpgrade](Resume-NAVDataUpgrade.md)

[Start-NAVDataUpgrade](Start-NAVDataUpgrade.md)

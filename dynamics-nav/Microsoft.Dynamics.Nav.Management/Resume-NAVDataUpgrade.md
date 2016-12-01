---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Resume-NAVDataUpgrade

## SYNOPSIS
Resumes a suspended data upgrade process.

## SYNTAX

### AllMethods (Default)
```
Resume-NAVDataUpgrade [[-Tenant] <TenantId>] [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

### SingleMethod
```
Resume-NAVDataUpgrade [[-Tenant] <TenantId>] [-CodeunitId] <Int32> [-FunctionName] <String>
 [[-CompanyName] <String>] [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
You can choose to re-run all previously failed and cancelled upgrade functions or choose a specific upgrade function. Only failed or cancelled upgrade functions can be re-run.

To get a list of invoked functions, use the Get-NAVDataUpgrade cmdlet. It is not possible to resume the data upgrade process if it was stopped by the Stop-NAVDataUpgrade cmdlet.

## EXAMPLES

### EXAMPLE 1
```
Resume-NAVDataUpgrade -ServerInstance DynamicsNAV
```

This example resumes a currently suspended data upgrade process.

### EXAMPLE 2
```
Resume-NAVDataUpgrade -ServerInstance DynamicsNAV -CodeunitId 111111 -FunctionName Upg1 -CompanyName
```

This example resumes currently suspended data upgrade process by invoking a specific upgrade function that previously failed or was cancelled.
This approach can be useful for gradually fixing and rerunning upgrade functions without having to restore the full database and start from beginning.

## PARAMETERS

### -CodeunitId
Specifies the ID of the upgrade codeunit to run.

```yaml
Type: Int32
Parameter Sets: SingleMethod
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompanyName
Specifies the name of the company for which to run the upgrade codeunit function.

```yaml
Type: String
Parameter Sets: SingleMethod
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FunctionName
Specifies the name of the upgrade function to run.

```yaml
Type: String
Parameter Sets: SingleMethod
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.
Include the name in single-quotes.

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
Specifies the ID of a tenant on the Microsoft Dynamics NAV Server instance.
You can omit the Tenant parameter only if the Microsoft Dynamics NAV Server instance is not configured to run multiple tenants.

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

## INPUTS

### System.String 
You can pass the value of the CodunitId, CompanyName, FunctionName, ServerInstance and Tenant parameters as a string to this cmdlet.

## OUTPUTS

## NOTES
## RELATED LINKS
[Get-NAVDataUpgrade](Get-NAVDataUpgrade.md)

[Start-NAVDataUpgrade](Start-NAVDataUpgrade.md)

[Stop-NAVDataUpgrade](Stop-NAVDataUpgrade.md)

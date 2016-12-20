---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401378
schema: 2.0.0
---

# New-NAVServerPermissionSet

## SYNOPSIS
Creates a new permission set.

## SYNTAX

```
New-NAVServerPermissionSet -PermissionSetId <String> -PermissionSetName <String> [-ServerInstance] <String>
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Use the New-NAVServerPermissionSet cmdlet to create a new permission set.
After you create a permission set with New-NAVServerPermissionSet, use New-NAVServerPermission to add individual permissions to the new permission set.

## EXAMPLES

### EXAMPLE 1
```
New-NAVServerPermissionSet MicrosoftDynamicsNavServer -PermissionSetId TEST -PermissionSetName 'This is a set for TEST.'
```

This example creates a new Microsoft Dynamics NAV permission set with Permission Set ID TEST and Permission Set Name 'This is a set for TEST.'

## PARAMETERS

### -PermissionSetId
Specifies an ID for the new permission set.
This is a string such as SAMPLE or ACCTS.
Avoid using the ID of an already existing permission set, otherwise the cmdlet returns an error.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PermissionSetName
Specifies a short description of the permission set.
Remember to use quotation marks around this string.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
You can pipe a string that contains a Microsoft Dynamics NAV Server instance name to the cmdlet.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NAVServerPermissionSet](Get-NAVServerPermissionSet.md)

[Remove-NAVServerPermissionSet](Remove-NAVServerPermissionSet.md)

[Set-NAVServerPermissionSet](Set-NAVServerPermissionSet.md)

[New-NAVServerPermission](New-NAVServerPermission.md)

[Get-NAVServerPermission](Get-NAVServerPermission.md)

[Remove-NAVServerPermission](Remove-NAVServerPermission.md)

[Set-NAVServerPermission](Set-NAVServerPermission.md)

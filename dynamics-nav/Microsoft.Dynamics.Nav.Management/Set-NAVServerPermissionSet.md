---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-NAVServerPermissionSet

## SYNOPSIS
Renames a Microsoft Dynamics NAV permission set.

## SYNTAX

```
Set-NAVServerPermissionSet -PermissionSetId <String> -PermissionSetName <String> [-ServerInstance] <String>
 [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Set-NAVServerPermissionSet cmdlet to change the name of an existing a Microsoft Dynamics NAV permission set.

## EXAMPLES

### EXAMPLE 1
```
Set-NAVServerPermissionSet DynamicsNAV -PermissionSetId Original -NewPermissionSetId Improved
```

Description

-----------

This example renames an existing permission set.

## PARAMETERS

### -PermissionSetId
Specifies the existing name (ID) for the permission set.

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
Specifies the name of the permission set.

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
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### None

## NOTES
## RELATED LINKS

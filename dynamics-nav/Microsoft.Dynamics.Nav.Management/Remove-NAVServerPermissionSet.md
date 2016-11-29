---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-NAVServerPermissionSet

## SYNOPSIS
Removes a Microsoft Dynamics NAV permission set.

## SYNTAX

```
Remove-NAVServerPermissionSet -PermissionSetId <String> [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm]
```

## DESCRIPTION
Use the Remove-NAVServerPermissionSet cmdlet to remove a permission set from the Microsoft Dynamics NAV database for a specific Microsoft Dynamics NAV Server instance.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Remove-NAVServerPermissionSet DynamicsNAV90 -PermissionSetId AVOCADO
```

Description

-----------

The example removes the AVOCADO permission set.

## PARAMETERS

### -PermissionSetId
Specifies the ID of a permission set, which is a string such as RES-JOURNAL or SUPER.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
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

### None

## NOTES
## RELATED LINKS


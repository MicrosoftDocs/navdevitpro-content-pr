---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-NAVServerPermission

## SYNOPSIS
Removes a permission from a permission set.

## SYNTAX

```
Remove-NAVServerPermission -PermissionSetId <String> -ObjectType <ObjectType> -ObjectId <Int32>
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Remove-NAVServerPermission cmdlet to remove a permission from a permission set.
You must specify a Permission Set ID, Object Type, and Object ID with the cmdlet.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Remove-NAVServerPermission DynamicsNAV -PermissionSetId AVOCADO -ObjectType TableData -ObjectId 18
```

Description

-----------

This example removes a permission from the permission set AVOCADO.

## PARAMETERS

### -ObjectId
Specifies the ID of the object that the permission applies to.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectType
Specifies an Object Type, such as TableData or Page.
Always remove spaces when specifying an Object Type.
You can also use integers to specify the Object Type.

TableData = 0

Table = 1

Form = 2

Report = 3

Dataport = 4

CodeUnit = 5

XmlPort = 6

MenuSuite = 7

Page = 8

Query = 9

System = 10

FieldNumber = 11

LimitedUsageTableData = 12

TablePage = 13

```yaml
Type: ObjectType
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PermissionSetId
Specifies the ID for a permission set, such as SUPER or BASIC.

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


---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Set-NAVServerPermission

## SYNOPSIS
Changes the values for an existing permission set.

## SYNTAX

```
Set-NAVServerPermission -PermissionSetId <String> -ObjectType <ObjectType> -ObjectId <Int32>
 [-SecurityFilter <String>] [-Read <PermissionOption>] [-Insert <PermissionOption>]
 [-Modify <PermissionOption>] [-Delete <PermissionOption>] [-Execute <PermissionOption>]
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Set-NAVServerPermission cmdlet to change the permissions that are granted by an existing permission set.

## EXAMPLES

### EXAMPLE 1
```
Set-NAVServerPermission DynamicsNAV -PermissionSetId BASIC -ObjectType Page -ObjectId 21 -Read Indirect
```
This example updates the Read permission for the specified page object to Indirect for the BASIC permission set.

## PARAMETERS

### -Delete
Specifies the delete permission for the object.
You can use either a string value (such as No) or a numeric value (such as 0).

No = 0

Yes = 1

Indirect = 2

```yaml
Type: PermissionOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Execute
Specifies the execute permission for the object.
You can use either a string value (such as No) or a numeric value (such as 0).

No = 0

Yes = 1

Indirect = 2

```yaml
Type: PermissionOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Insert
Specifies the insert permission for the object.
You can use either a string value (such as No) or a numeric value (such as 0).

No = 0

Yes = 1

Indirect = 2

```yaml
Type: PermissionOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Modify
Specifies the modify permission for the object.
You can use either a string value (such as No) or a numeric value (such as 0).

No = 0

Yes = 1

Indirect = 2

```yaml
Type: PermissionOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
Specifies the ID of the object that the permission applies to.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectType
Specifies the type of the object the permission applies to.
You can use either a string value (such as TableData) or a numeric value (such as 0).

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

```yaml
Type: ObjectType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PermissionSetId
The ID of the permission set that you are updating, such as BASIC or SUPER.

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

### -Read
Specifies the read permission for the object.
You can use either a string value (such as No) or a numeric value (such as 0).

No = 0

Yes = 1

Indirect = 2

```yaml
Type: PermissionOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecurityFilter
Specifies a security filter for the permission.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
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

### System.String
You can pipe a string that contains a Microsoft Dynamics NAV Server instance name to the cmdlet.

## OUTPUTS

### None

## NOTES
## RELATED LINKS
[Get-NAVServerPermission](Get-NAVServerPermission.md)  

[New-NAVServerPermission](New-NAVServerPermission.md)  

[Remove-NAVServerPermission](Remove-NAVServerPermission.md)  

[Get-NAVServerPermissionSet](Get-NAVServerPermissionSet.md)  

[New-NAVServerPermissionSet](New-NAVServerPermissionSet.md)  

[Remove-NAVServerPermissionSet](Remove-NAVServerPermissionSet.md)  

[Set-NAVServerPermissionSet](Set-NAVServerPermissionSet.md)  

---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401377
schema: 2.0.0
---

# New-NAVServerPermission

## SYNOPSIS
Adds a permission to a permission set.

## SYNTAX

```
New-NAVServerPermission -PermissionSetId <String> -ObjectType <ObjectType> -ObjectId <Int32>
 [-SecurityFilter <String>] [-Read <PermissionOption>] [-Insert <PermissionOption>]
 [-Modify <PermissionOption>] [-Delete <PermissionOption>] [-Execute <PermissionOption>]
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Use the New-NAVServerPermission cmdlet to add a permission to a permission set.

## EXAMPLES

### EXAMPLE 1
```
Set-NAVServerPermission DynamicsNAV -PermissionSetId BASIC -ObjectType Page -ObjectId 21 -Read Indirect
```

This example updates the Read permission for the specified page object to Indirect for the BASIC permission set.

## PARAMETERS

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
Accepted values: TableData, Table, Form, Report, Dataport, CodeUnit, XmlPort, MenuSuite, Page, Query, System, FieldNumber, LimitedUsageTableData, TablePage, PageExtension, TableExtension

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectId
Specifies the ID of the object the permission applies to.

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

### -Read
Specifies whether the permission includes read permission for the object.
You can use either a string value (such as No) or a numeric value (such as 0).

No = 0

Yes = 1

Indirect = 2

```yaml
Type: PermissionOption
Parameter Sets: (All)
Aliases: 
Accepted values: No, Yes, Indirect

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Insert
Specifies whether the permission includes insert permission for the object.
You can use either a string value (such as No) or a numeric value (such as 0).

No = 0

Yes = 1

Indirect = 2

```yaml
Type: PermissionOption
Parameter Sets: (All)
Aliases: 
Accepted values: No, Yes, Indirect

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Modify
Specifies whether the permission includes modify permission for the object.
You can use either a string value (such as No) or a numeric value (such as 0).

No = 0

Yes = 1

Indirect = 2

```yaml
Type: PermissionOption
Parameter Sets: (All)
Aliases: 
Accepted values: No, Yes, Indirect

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Delete
Specifies whether the permission includes delete permission for the object.
You can use either a string value (such as No) or a numeric value (such as 0).

No = 0

Yes = 1

Indirect = 2

```yaml
Type: PermissionOption
Parameter Sets: (All)
Aliases: 
Accepted values: No, Yes, Indirect

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Execute
Specifies whether the permission includes execute permission for the object.
You can use either a string value (such as No) or a numeric value (such as 0).

No = 0

Yes = 1

Indirect = 2

```yaml
Type: PermissionOption
Parameter Sets: (All)
Aliases: 
Accepted values: No, Yes, Indirect

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

[Get-NAVServerPermission](Get-NAVServerPermission.md)

[Remove-NAVServerPermission](Remove-NAVServerPermission.md)

[Set-NAVServerPermission](Set-NAVServerPermission.md)

[Get-NAVServerPermissionSet](Get-NAVServerPermissionSet.md)

[New-NAVServerPermissionSet](New-NAVServerPermissionSet.md)

[Remove-NAVServerPermissionSet](Remove-NAVServerPermissionSet.md)

[Set-NAVServerPermissionSet](Set-NAVServerPermissionSet.md)

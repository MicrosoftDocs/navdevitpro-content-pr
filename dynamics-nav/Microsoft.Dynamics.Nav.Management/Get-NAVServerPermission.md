---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-NAVServerPermission

## SYNOPSIS
Returns information about the permissions that are applied to Microsoft Dynamics NAV objects for the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Get-NAVServerPermission [-PermissionSetId <String>] [-ObjectType <ObjectType>] [-ObjectId <Int32>]
 [-ServerInstance] <String> [-Force]
```

## DESCRIPTION
Use the Get-NAVServerPermission cmdlet to return a list of Microsoft Dynamics NAV permissions that are applied to Microsoft Dynamics NAV objects for the specified Microsoft Dynamics NAV Server instance.
You can filter the information permission set ID, object type, and/or object ID.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-NavServerPermission nav_server_instance -ObjectId 7700

PermissionSet ID   : ADCS ALL
Object Type        : Table Data
Object ID          : 7700
Read Permission    : Yes
Insert Permission  :
Modify Permission  :
Delete Permission  :
Execute Permission :
Security Filter    :
PermissionSet Name : ADCS User
Object Name        : Miniform Header

PermissionSet ID   : ADCS SETUP
Object Type        : Table Data
Object ID          : 7700
Read Permission    : Yes
Insert Permission  : Yes
Modify Permission  : Yes
Delete Permission  : Yes
Execute Permission :
Security Filter    :
PermissionSet Name : ADCS Set-up
Object Name        : Miniform Header
```

Description

-----------

This example returns information about all permission sets that include permissions for object 7700.

## PARAMETERS

### -ObjectId
Specifies an Object ID, such as 7702.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ObjectType
Specifies an Object Type, such as TableData or Page.
Always remove spaces when specifying an Object Type.
You can also use integers to specify the Object Type:

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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PermissionSetId
Specifies the ID for a permission set, such as SUPER or BASIC.

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

### System.Data.DataTable

## NOTES
## RELATED LINKS


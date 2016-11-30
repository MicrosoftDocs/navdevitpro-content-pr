---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-NAVServerUserPermissionSet

## SYNOPSIS
Removes a permission set from the list of permission sets that are assigned to a Microsoft Dynamics NAV user.

## SYNTAX

### WindowsAccount (Default)
```
Remove-NAVServerUserPermissionSet [-Scope <PermissionScope>] [-AppName <String>] [-AppPublisher <String>]
 [-Tenant <TenantId>] [-CompanyName <String>] -PermissionSetId <String> -WindowsAccount <String>
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

### Sid
```
Remove-NAVServerUserPermissionSet [-Scope <PermissionScope>] [-AppName <String>] [-AppPublisher <String>]
 [-Tenant <TenantId>] [-CompanyName <String>] -PermissionSetId <String> -Sid <String>
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

### UserName
```
Remove-NAVServerUserPermissionSet [-Scope <PermissionScope>] [-AppName <String>] [-AppPublisher <String>]
 [-Tenant <TenantId>] [-CompanyName <String>] -PermissionSetId <String> -UserName <String>
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

### InputObject
```
Remove-NAVServerUserPermissionSet [-Scope <PermissionScope>] [-AppName <String>] [-AppPublisher <String>]
 [-Tenant <TenantId>] [-CompanyName <String>] -PermissionSetId <String> -InputObject <DataRow>
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Remove-NAVServerUserPermissionSet cmdlet to remove a permission set that is assigned to a Microsoft Dynamics NAV user.
You can use the Get-NAVServerUserPermissionSet cmdlet to determine which permission sets are currently assigned to a particular user.

## EXAMPLES

### EXAMPLE 1
```
Remove-NAVServerUserPermissionSet DynamicsNAV -Sid S-1-5-20 -PermissionSetId AVOCADO
```

Description

-----------

This example removes the built-in account (Network Service) from the AVOCADO permission set.

## PARAMETERS

### -AppName
Specifies the name of the Dynamics NAV extension.

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

### -AppPublisher
Specifies the publisher of the Dynamics NAV extension.

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

### -CompanyName
Specifies the name of a company in the Microsoft Dynamics NAV database.
The specified user permission sets are removed for that company only.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the DataRow object that identifies the user to remove the permission set from.
You can pass this object from the Get-NAVServerUserPermissionSet cmdlet.

```yaml
Type: DataRow
Parameter Sets: InputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### -Scope
Not Specified.

```yaml
Type: PermissionScope
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

### -Sid
Specifies a security identifier (SID) of the Microsoft Dynamics NAV user.
The SID is a unique value that identifies a Windows user account.
You can use the Sid, UserName, or WindowsAccount parameters to identify the  user.
If you use the Sid parameter, then do not set the UserName or WindowsAccount parameters.

```yaml
Type: String
Parameter Sets: Sid
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant
Specifies the ID of the tenant that is mounted of the Microsoft Dynamics NAV Server instance to which the user belongs.
You can omit the Tenant parameter only if the Microsoft Dynamics NAV Server instance is not configured to run multiple tenants.

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

### -UserName
Specifies the user name of the Microsoft Dynamics NAV user.
The user name is defined by the User Name field in a user's account in Microsoft Dynamics NAV.
You can use the UserName, WindowsAccount or Sid parameters to identify the user.
If you use the Username parameter, then you cannot use the Windows Account or Sid parameters.

```yaml
Type: String
Parameter Sets: UserName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsAccount
Specifies the Windows user name of the Microsoft Dynamics NAV user.
The value has the domain\username format.
You can use either the WindowsAccount, UserName, or Sid parameters to identify the user.
If you use the WindowsAccount parameter, then you cannot use the UserName or Sid parameters.

```yaml
Type: String
Parameter Sets: WindowsAccount
Aliases: 

Required: True
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


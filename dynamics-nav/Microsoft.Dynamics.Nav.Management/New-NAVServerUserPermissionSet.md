---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401380
schema: 2.0.0
---

# New-NAVServerUserPermissionSet

## SYNOPSIS
Assigns a permission set to a Microsoft Dynamics NAV user.

## SYNTAX

### WindowsAccount (Default)
```
New-NAVServerUserPermissionSet [-Scope <PermissionScope>] [-AppName <String>] [-AppPublisher <String>]
 [-Tenant <TenantId>] [-CompanyName <String>] -PermissionSetId <String> -WindowsAccount <String>
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Sid
```
New-NAVServerUserPermissionSet [-Scope <PermissionScope>] [-AppName <String>] [-AppPublisher <String>]
 [-Tenant <TenantId>] [-CompanyName <String>] -PermissionSetId <String> -Sid <String>
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UserName
```
New-NAVServerUserPermissionSet [-Scope <PermissionScope>] [-AppName <String>] [-AppPublisher <String>]
 [-Tenant <TenantId>] [-CompanyName <String>] -PermissionSetId <String> -UserName <String>
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Use the New-NAVServerUserPermissionSet cmdlet to assign a permission set to a Microsoft Dynamics NAV user.

Use the UserName, Sid or the WindowsAccount parameter to identify the user. Use the PermissionSetID parameter to identify the permission set.

## EXAMPLES

### EXAMPLE 1
```
New-NAVServerUserPermissionSet DynamicsNAV -WindowsAccount cronus\chris -PermissionSetId BASIC
```

This example adds the BASIC permission set for Windows user Cronus\Chris.

## PARAMETERS

### -Scope
Specifies whether the permission set that you want to apply is a System or Tenant permission set. A System permission set is a permission set that is stored in table 2000000004 Permission Set of the application database, and will apply to all tenants in the system. A Tenant permission set is a permission set that is stored in table 2000000166 Tenant Permission Set of the tenant database, and will apply to specific tenants. Tenant permission sets are primarily used with NAV extensions.

```yaml
Type: PermissionScope
Parameter Sets: (All)
Aliases: 
Accepted values: System, Tenant

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Tenant
Specifies a ID of the tenant that is mounted on the Microsoft Dynamics NAV Server instance.

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

### -CompanyName
The name of the Microsoft Dynamics NAV company on which to apply the permission set.

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

### -PermissionSetId
The ID of an existing permission set in the Microsoft Dynamics NAV database, such as SUPER, CASHFLOW, or BASIC.

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

### -Sid
Specifies a security identifier (SID) for a Microsoft Dynamics NAV user. The SID is a unique value that identifies a Windows user account.

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

### -WindowsAccount
Specifies the Windows user name of a Microsoft Dynamics NAV user to assign the permission set to. The value has the domain\username format.

You can use the WindowsAccount, UserName, or Sid parameters to identify the user. If you use the WindowsAccount parameter, then you cannot use the UserName or Sid parameters.

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

### -UserName
Specifies the user name of the Microsoft Dynamics NAV user to assign the permission set to. The user name is defined by the User Name field in a user's account in Microsoft Dynamics NAV.

You can use the UserName, WindowsAccount or Sid parameters to identify the user. If you use the Username parameter, then you cannot use the Windows Account or Sid parameters.

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

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance. You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

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

[Get-NAVServerUserPermissionSet](Get-NAVServerUserPermissionSet.md)

[Remove-NAVServerUserPermissionSet](Remove-NAVServerUserPermissionSet.md)

[Get-NAVServerUser](Get-NAVServerUser.md)

[New-NAVServerUser](New-NAVServerUser.md)

[Remove-NAVServerUser](Remove-NAVServerUser.md)

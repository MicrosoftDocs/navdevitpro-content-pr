---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-NAVServerUserPermissionSet

## SYNOPSIS
Returns permission set information for Microsoft Dynamics NAV users.

## SYNTAX

```
Get-NAVServerUserPermissionSet [-AppName <String>] [-AppPublisher <String>] [-Tenant <TenantId>]
 [-CompanyName <String>] [-PermissionSetId <String>] [-Sid <String>] [-WindowsAccount <String>]
 [-UserName <String>] [-ServerInstance] <String> [-Force]
```

## DESCRIPTION
Use the Get-NAVServerUserPermissionSet cmdlet to return permission set information for a Microsoft Dynamics NAV user.
Specifically, the cmdlet returns the following information for each relevant user:

User Security ID  
PermissionSet  
Company Name  
User Name  
Permission Set Name  

You can also use any one of these values, or any combination of these values, to filter the return.

## EXAMPLES

### EXAMPLE 1
```
Get-NAVServerUserPermissionSet DynamicsNAV
```

This example returns permission sets for all current nav_now users.

### EXAMPLE 2
```
Get-NAVServerUserPermissionSet DynamicsNAV -WindowsAccount cronus\chris

User Security ID   : b5013678-36e5-4469-8f07-dcc453fed66f
PermissionSet ID   : SUPER
Company Name       : CRONUS International Ltd
User Name          : cronuschris
PermissionSet Name : This role has all permissions.
```

This example returns information for a specific user, filtered by the user's Windows account name.

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
Specifies the publisher of the Dynamics NAV extension, such as Microsoft.

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
The name of a company in the Microsoft Dynamics NAV database. If this argument is not included in the cmdlet, users in the default company are returned.

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
The ID of a permission set, such as RES-JOURNAL or SUPER.

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

### -Sid
Specifies a security identifier (SID) of a Microsoft Dynamics NAV user. The SID is a unique value that identifies a Windows user account.

You can use the Sid, UserName, or WindowsAccount parameters to identify the user.
If you use the Sid parameter, then do not set the UserName or WindowsAccount parameters.

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
Specifies the tenant ID of the database to which the Microsoft Dynamics NAV user belongs that is mounted on the Microsoft Dynamics NAV instance.

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
Specifies the user name of a Microsoft Dynamics NAV user. The user name is defined by the User Name field in a user's account in Microsoft Dynamics NAV.

You can use the UserName, WindowsAccount or Sid parameters to identify the user.
If you use the Username parameter, then you cannot use the Windows Account or Sid parameters.

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

### -WindowsAccount
Specifies the Windows user name of a Microsoft Dynamics NAV user. The value has the domain\username format.

You can use the WindowsAccount, UserName, or Sid parameters to identify the user.
If you use the WindowsAccount parameter, then you cannot use the UserName or Sid parameters.

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

### System.Data.DataTable
Returns the permission set information as a table.

## NOTES
## RELATED LINKS

[New-NAVServerPermissionSet](New-NAVServerPermissionSet.md)  

[Remove-NAVServerUserPermissionSet](Remove-NAVServerUserPermissionSet.md)  

[Get-NAVServerUser](Get-NAVServerUser.md)  

[New-NAVServerUser](New-NAVServerUser.md)  

[Remove-NAVServerUser](Remove-NAVServerUser.md)  

[Set-NAVServerUser](Set-NAVServerUser.md)  

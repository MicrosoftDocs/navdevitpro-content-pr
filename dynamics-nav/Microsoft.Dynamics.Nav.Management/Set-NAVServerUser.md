---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401398
schema: 2.0.0
---

# Set-NAVServerUser

## SYNOPSIS
Changes the configuration settings of an existing Microsoft Dynamics NAV user.

## SYNTAX

### WindowsAccount (Default)
```
Set-NAVServerUser [-Tenant <TenantId>] [-NewWindowsAccount <String>] -WindowsAccount <String>
 [-NewUserName <String>] [-FullName <String>] [-State <NavUserState>] [-ExpiryDate <DateTime>]
 [-LicenseType <LicenseType>] [-AuthenticationKey <String>] [-ContactEmail <String>]
 [-AuthenticationEmail <String>] [-CreateWebServicesKey] [-WebServicesKeyExpiryDate <DateTime>]
 [-ProfileId <String>] [-AuthenticationObjectId <String>] [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Sid
```
Set-NAVServerUser [-Tenant <TenantId>] [-NewWindowsAccount <String>] -Sid <String> [-NewUserName <String>]
 [-FullName <String>] [-State <NavUserState>] [-ExpiryDate <DateTime>] [-LicenseType <LicenseType>]
 [-AuthenticationKey <String>] [-ContactEmail <String>] [-AuthenticationEmail <String>] [-CreateWebServicesKey]
 [-WebServicesKeyExpiryDate <DateTime>] [-ProfileId <String>] [-AuthenticationObjectId <String>]
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SidPass
```
Set-NAVServerUser [-Tenant <TenantId>] [-NewWindowsAccount <String>] -Sid <String> [-NewUserName <String>]
 [-FullName <String>] [-State <NavUserState>] [-ExpiryDate <DateTime>] [-ChangePasswordAtNextLogOn]
 [-LicenseType <LicenseType>] -Password <SecureString> [-AuthenticationKey <String>] [-ContactEmail <String>]
 [-AuthenticationEmail <String>] [-CreateWebServicesKey] [-WebServicesKeyExpiryDate <DateTime>]
 [-ProfileId <String>] [-AuthenticationObjectId <String>] [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### WindowsAccountPass
```
Set-NAVServerUser [-Tenant <TenantId>] [-NewWindowsAccount <String>] -WindowsAccount <String>
 [-NewUserName <String>] [-FullName <String>] [-State <NavUserState>] [-ExpiryDate <DateTime>]
 [-ChangePasswordAtNextLogOn] [-LicenseType <LicenseType>] -Password <SecureString>
 [-AuthenticationKey <String>] [-ContactEmail <String>] [-AuthenticationEmail <String>] [-CreateWebServicesKey]
 [-WebServicesKeyExpiryDate <DateTime>] [-ProfileId <String>] [-AuthenticationObjectId <String>]
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UserName
```
Set-NAVServerUser [-Tenant <TenantId>] [-NewWindowsAccount <String>] -UserName <String> [-NewUserName <String>]
 [-FullName <String>] [-State <NavUserState>] [-ExpiryDate <DateTime>] [-LicenseType <LicenseType>]
 [-AuthenticationKey <String>] [-ContactEmail <String>] [-AuthenticationEmail <String>] [-CreateWebServicesKey]
 [-WebServicesKeyExpiryDate <DateTime>] [-ProfileId <String>] [-AuthenticationObjectId <String>]
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UserNamePass
```
Set-NAVServerUser [-Tenant <TenantId>] [-NewWindowsAccount <String>] -UserName <String> [-NewUserName <String>]
 [-FullName <String>] [-State <NavUserState>] [-ExpiryDate <DateTime>] [-ChangePasswordAtNextLogOn]
 [-LicenseType <LicenseType>] -Password <SecureString> [-AuthenticationKey <String>] [-ContactEmail <String>]
 [-AuthenticationEmail <String>] [-CreateWebServicesKey] [-WebServicesKeyExpiryDate <DateTime>]
 [-ProfileId <String>] [-AuthenticationObjectId <String>] [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### AppId
```
Set-NAVServerUser [-Tenant <TenantId>] [-NewWindowsAccount <String>] -UserName <String> [-NewUserName <String>]
 [-FullName <String>] [-State <NavUserState>] [-ExpiryDate <DateTime>] [-AuthenticationKey <String>]
 [-ContactEmail <String>] -ApplicationId <Guid> [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Use the Set-NAVServerUser cmdlet to rename an existing Microsoft Dynamics NAV user or change other configuration parameters that are related to the user.

## EXAMPLES

### EXAMPLE 1
```
Set-NAVServerUser DynamicsNAV90 -Sid S-1-5-20 -NewWindowsAccount MyDomain\User1
```

This example renames the Windows account user name of a Microsoft Dynamics NAV user.
The existing Microsoft Dynamics NAV user is identified by its Sid.

### EXAMPLE 2
```
Set-NAVServerUser DynamicsNAV -WindowsAccount MyDomain\User1 -NewWindowsAccount MyDomain\User2
```

This example changes the Windows user name that is assigned to Microsoft Dynamics NAV user.
The existing Microsoft Dynamics NAV user is identified by its current Windows user name by the WindowsAccount parameter.

### EXAMPLE 3
```
Set-NAVServerUser DynamicsNAV90 -UserName USER1 -NewUserName USER2 -ChangePasswordAtNextLogOn -Password (Read-Host "Enter password for USER2" -AsSecureString)Enter password for USER2: ************
```

This example changes the user name of a Microsoft Dynamics NAV user from USER1 to USER2.
It also changes the user's password and requires that the user change the password the next time he logs on to Microsoft Dynamics NAV.

## PARAMETERS

### -Tenant
Specifies the ID of the tenant of the Microsoft Dynamics NAV Server instance that the user is stored in.

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

### -NewWindowsAccount
Specifies the new Windows user name for the Microsoft Dynamics NAV user that you want to change. The value has the domain\username format.

You cannot use the NewWindowsAccount parameter and NewUserName parameter in the same command.

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

### -Sid
Specifies the security identifier (SID) of the Microsoft Dynamics NAV user that you want to change. The SID is a unique value that identifies a Windows user account.

You can use the Sid, UserName, or WindowsAccount parameters to create the user. If you use the Sid parameter, then you cannot set the UserName or WindowsAccount parameters.

```yaml
Type: String
Parameter Sets: Sid, SidPass
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsAccount
Specifies the Windows account user name of the existing Microsoft Dynamics NAV user that you want to change.
The value has the domain\username format.
You can use the WindowsAccount, UserName, or Sid parameters to create the user.
If you use the WindowsAccount parameter, then you cannot use the UserName or Sid parameters.

```yaml
Type: String
Parameter Sets: WindowsAccount, WindowsAccountPass
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies the user name of the existing Microsoft Dynamics NAV user that you want to change. The user name appears in the User Name field in a user's account in Microsoft Dynamics NAV.

You can use the UserName, WindowsAccount or Sid parameters to identify the user. If you use the Username parameter, then you cannot use the Windows Account or Sid parameters.

```yaml
Type: String
Parameter Sets: UserName, UserNamePass, AppId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewUserName
Specifies the new user name to assign the Microsoft Dynamics NAV user.
The user name is defined by the User Name field in the user's account in Microsoft Dynamics NAV.

You cannot use the NewUserName parameter and NewWindowsAccount parameter in the same command.

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

### -FullName
Sets the full name of the user.

On the User card in Microsoft Dynamics NAV, this value appears in the Full Name field.
The value typically includes the user's first and last name.

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

### -State
Sets the current state of the user's access to Microsoft Dynamics NAV.
The parameters has the following values (you can use either the text value of the integer value in parenthesis:

Enabled (0)

Disabled (1)

```yaml
Type: NavUserState
Parameter Sets: (All)
Aliases: 
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpiryDate
Specifies when the user's access to Microsoft Dynamics NAV expires.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ChangePasswordAtNextLogOn
Forces the user to change the password the next time that the user logs on.

```yaml
Type: SwitchParameter
Parameter Sets: SidPass, WindowsAccountPass, UserNamePass
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseType
Specifies the license type to assign the user.
The parameter has the following values (you can use either the text value or the integer in the parenthesis):

Full (0)

Limited (1)

DeviceOnly (2)

WindowsGroup (3) - Use this license type if the Microsoft Dynamics NAV user is based on a Windows group in Active Directory. This user account cannot log on to Microsoft Dynamics NAV.
Instead, it is used to map the permission set to the individual Windows users in the Windows user group. You must apply the license type to the individual users in the Windows user group.

External (4)

```yaml
Type: LicenseType
Parameter Sets: WindowsAccount, Sid, SidPass, WindowsAccountPass, UserName, UserNamePass
Aliases: 
Accepted values: Full, Limited, DeviceOnly, WindowsGroup, External

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies a protected password for the Microsoft Dynamics NAV user.

The password is only used when the credential type for authenticating users who try to access Microsoft Dynamics NAV is set to NavUserPassword.

```yaml
Type: SecureString
Parameter Sets: SidPass, WindowsAccountPass, UserNamePass
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationKey
Specifies the authentication key for authenticating with Microsoft Azure Access Control Service (ACS).

This key must be at least 8 characters and a combination of uppercase and lowercase letters and numbers.

The authentication key is entered by the user the first time that the user logs on to Microsoft Dynamics NAV.

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

### -ContactEmail
Specifies the contact email address for the Microsoft Dynamics NAV user.

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

### -AuthenticationEmail
Specifies the Microsoft account that this user uses to access Office 365 and SharePoint. The authentication email address must be the Microsoft account that the users log in to Office 365 with, such as an account from Microsoft Azure Active Directory (Azure AAD).

```yaml
Type: String
Parameter Sets: WindowsAccount, Sid, SidPass, WindowsAccountPass, UserName, UserNamePass
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateWebServicesKey
Creates a web services access key for the user. The web service access key is automatically generated.

This parameter is relevant only when Microsoft Dynamics NAV is configured to use either the NavUserPassword or AccessControlService credential type for authenticating users. The web service access key is used instead of a password to authenticate web service requests, such as SOAP and OData.

```yaml
Type: SwitchParameter
Parameter Sets: WindowsAccount, Sid, SidPass, WindowsAccountPass, UserName, UserNamePass
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebServicesKeyExpiryDate
Specifies the date and time when the user's web services access key expires.

```yaml
Type: DateTime
Parameter Sets: WindowsAccount, Sid, SidPass, WindowsAccountPass, UserName, UserNamePass
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileId
Specifies the ID of a profile to assign the user.

```yaml
Type: String
Parameter Sets: WindowsAccount, Sid, SidPass, WindowsAccountPass, UserName, UserNamePass
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationId
Identifies the application this user represents. This requires that the application is registered in Azure Active Directory. The application is identified by its "client id" in Azure Active Directory.

```yaml
Type: Guid
Parameter Sets: AppId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationObjectId
Specifies the Microsoft account that this user uses to access Office 365 and SharePoint. The authentication object id must be the Microsoft account that the users log in to Office 365 with, such as an account from Microsoft Azure Active Directory (Azure AAD).

```yaml
Type: String
Parameter Sets: WindowsAccount, Sid, SidPass, WindowsAccountPass, UserName, UserNamePass
Aliases: 

Required: False
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

[Get-NAVServerUser](Get-NAVServerUser.md)

[New-NAVServerUser](New-NAVServerUser.md)

[Remove-NAVServerUser](Remove-NAVServerUser.md)

[Get-NAVServerUserPermissionSet](Get-NAVServerUserPermissionSet.md)

[New-NAVServerPermissionSet](New-NAVServerPermissionSet.md)

[Remove-NAVServerUserPermissionSet](Remove-NAVServerUserPermissionSet.md)

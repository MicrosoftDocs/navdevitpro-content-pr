---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# New-NAVServerUser

## SYNOPSIS
Creates a new Microsoft Dynamics NAV user.

## SYNTAX

### WindowsAccount (Default)
```
New-NAVServerUser [-Tenant <TenantId>] -WindowsAccount <String> [-FullName <String>] [-State <NavUserState>]
 [-ExpiryDate <DateTime>] [-ChangePasswordAtNextLogOn] [-LicenseType <LicenseType>] [-Password <SecureString>]
 [-AuthenticationKey <String>] [-AuthenticationEmail <String>] [-ContactEmail <String>] [-CreateWebServicesKey]
 [-WebServicesKeyExpiryDate <DateTime>] [-ProfileId <String>] [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm]
```

### Sid
```
New-NAVServerUser [-Tenant <TenantId>] -Sid <String> [-FullName <String>] [-State <NavUserState>]
 [-ExpiryDate <DateTime>] [-ChangePasswordAtNextLogOn] [-LicenseType <LicenseType>] [-Password <SecureString>]
 [-AuthenticationKey <String>] [-AuthenticationEmail <String>] [-ContactEmail <String>] [-CreateWebServicesKey]
 [-WebServicesKeyExpiryDate <DateTime>] [-ProfileId <String>] [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm]
```

### UserName
```
New-NAVServerUser [-Tenant <TenantId>] -UserName <String> [-FullName <String>] [-State <NavUserState>]
 [-ExpiryDate <DateTime>] [-ChangePasswordAtNextLogOn] [-LicenseType <LicenseType>] [-Password <SecureString>]
 [-AuthenticationKey <String>] [-AuthenticationEmail <String>] [-ContactEmail <String>] [-CreateWebServicesKey]
 [-WebServicesKeyExpiryDate <DateTime>] [-ProfileId <String>] [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm]
```

### AppId
```
New-NAVServerUser [-Tenant <TenantId>] -UserName <String> [-FullName <String>] [-State <NavUserState>]
 [-ExpiryDate <DateTime>] [-AuthenticationKey <String>] [-ContactEmail <String>] -ApplicationId <Guid>
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the New-NAVServerUser cmdlet to create a new Microsoft Dynamics NAV user.
Anonymous accounts such as S-1-1-0 (Everyone) and S-1-5-7 (Anonymous) are not allowed.

## EXAMPLES

### EXAMPLE 1
```
New-NAVServerUser DynamicsNAV -Sid S-1-5-20
```

This example creates a new Microsoft Dynamics NAV user based on the built-in NT AUTHORITY\NETWORK SERVICE account in Windows.

### EXAMPLE 2
```
New-NAVServerUser MicrosoftDynamicsNavServer -WindowsAccount Cronus\Chris
```

This example creates a new Microsoft Dynamics NAV user based on a Windows user account that has the user name Chris from the domain Cronus.

### EXAMPLE 3
```
New-NAVServerUser navserver1 -UserName Chris -Password (Read-Host "Enter password for User1" -AsSecureString) -Verbose

Enter password for User1: ****
VERBOSE: NavCommand.BeginProcessing
VERBOSE: NavCommand.ProcessRecord
VERBOSE: Opening admin connection to ServerInstance 'MicrosoftDynamicsNavServer$navserver1'
VERBOSE: Admin connection to ServerInstance 'MicrosoftDynamicsNavServer$navserver1' has been opened
VERBOSE: Performing operation "New-NavServerUser" on target "ServerInstance = MicrosoftDynamicsNavServer$navserver1
VERBOSE: NavCommand.EndProcessing
VERBOSE: Closing admin connection to ServerInstance 'MicrosoftDynamicsNavServer$navserver1'
VERBOSE: Admin connection to ServerInstance 'MicrosoftDynamicsNavServer$navserver1' has been closed
```

This example creates a new Microsoft Dynamics NAV user that has the user name Chris and a password that is entered as a secure string (****).

### EXAMPLE 4
```
New-NAVServerUser navserver1 -UserName Chris -Password (ConvertTo-SecureString 'Password1234' -AsPlainText -Force)
```

This example creates a new Microsoft Dynamics NAV user that has the user name Chris and password Password1234.

### EXAMPLE 5
```
New-NAVServerUser navserver1 -CreateWebServicesKey -UserName Chris -WebServicesKeyExpiryDate '01-01-2014'
```

This example creates a new Microsoft Dynamics NAV user that has the user name Chris and a web services access key for logging on to Microsoft Dynamics NAV.
The web services acces key expires on 01-01-2014.

## PARAMETERS

### -ApplicationId
Identifies the application this user represents.
This requires that the application is registered in Azure Active Directory.
The application is identified by its "client id" in Azure Active Directory.

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

### -AuthenticationEmail
Specifies the Microsoft account that this user uses to access Office 365 and SharePoint.
The authentication email address must be the Microsoft account that the users log in to Office 365 with, such as an account from Windows Azure Active Directory (AAD).

```yaml
Type: String
Parameter Sets: WindowsAccount, Sid, UserName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationKey
Specifies the authentication key for authentication with Windows Azure Access Control Service (ACS). This key must be at least 8 characters and contain combination of uppercase and lowercase letters and numbers. The authentication key is entered by the user the first time that the user logs on to Microsoft Dynamics NAV.

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

### -ChangePasswordAtNextLogOn
Forces the user to change the password the next time that the user logs on.

```yaml
Type: SwitchParameter
Parameter Sets: WindowsAccount, Sid, UserName
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

### -CreateWebServicesKey
Creates a web services access key for the user. The web service access key is automatically generated. This parameter is relevant only when Microsoft Dynamics NAV is configured to use either the NavUserPassword or AccessControlService credential type for authenticating users.
The web service access key is used instead of a password to authenticate web service requests, such as SOAP and OData.

```yaml
Type: SwitchParameter
Parameter Sets: WindowsAccount, Sid, UserName
Aliases:

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

### -FullName
Specifies the user's full name.
This is typically includes the user's first and last name.
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

### -LicenseType
Specifies the license type to assign the user.
The parameter has the following values (you can use either the text value or the integer in parenthesis):

Full (0)

Limited (1)

DeviceOnly (2)

WindowsGroup (3) - Use this license type if the Microsoft Dynamics NAV user is based on a Windows group in Active Directory. This user account cannot log on to Microsoft Dynamics NAV.
Instead, it is used to map the permission set to the individual Windows users in the Windows user group. You must apply the license type to the individual users in the Windows user group.

External (4)

```yaml
Type: LicenseType
Parameter Sets: WindowsAccount, Sid, UserName
Aliases:

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
Parameter Sets: WindowsAccount, Sid, UserName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileId
Specifies the ID of the profile to assign the user.

```yaml
Type: String
Parameter Sets: WindowsAccount, Sid, UserName
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
Specifies the security identifier (SID) of the Windows user account for the user that you want to set up as a Microsoft Dynamics NAV user. The SID is a unique value that identifies a Windows user account. You can use the Sid, UserName, or WindowsAccount parameters to create the user. If you use the Sid parameter, then you cannot set the UserName or WindowsAccount parameters.

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

### -State
Specifies the state of the user's account and access to Microsoft Dynamics NAV.
The parameters has the following values (you can use either the text value of the integer value in parenthesis:

Enabled (0)

Disabled (1)

```yaml
Type: NavUserState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant
Specifies the ID of the tenant of the Microsoft Dynamics NAV Server instance on which to add the user. You can omit the Tenant parameter only if the Microsoft Dynamics NAV Server instance is not configured to run multiple tenants.

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
Specifies the user name for the new Microsoft Dynamics NAV user. The user name appears in the User Name field in a user's account in Microsoft Dynamics NAV. You can use the UserName, WindowsAccount or Sid parameters to identify the user. If you use the Username parameter, then you cannot use the Windows Account or Sid parameters.

```yaml
Type: String
Parameter Sets: UserName, AppId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebServicesKeyExpiryDate
Specifies the date and time that the user's web services access key expires.

```yaml
Type: DateTime
Parameter Sets: WindowsAccount, Sid, UserName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsAccount
Specifies the Windows account user name of the user that you want to set up as a Microsoft Dynamics NAV user. The value has the domain\username format. You can use the WindowsAccount, UserName, or Sid parameters to create the user. If you use the WindowsAccount parameter, then you cannot use the UserName or Sid parameters.

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
[Get-NAVServerUser](Get-NAVServerUser.md)  

[Remove-NAVServerUser](Remove-NAVServerUser.md)  

[Set-NAVServerUser](Set-NAVServerUser.md)  

[Get-NAVServerUserPermissionSet](Get-NAVServerUserPermissionSet.md)  

[New-NAVServerPermissionSet](New-NAVServerPermissionSet.md)  

[Remove-NAVServerUserPermissionSet](Remove-NAVServerUserPermissionSet.md)  

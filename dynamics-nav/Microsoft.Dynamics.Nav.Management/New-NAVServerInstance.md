---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401376
schema: 2.0.0
---

# New-NAVServerInstance

## SYNOPSIS
Creates a new Microsoft Dynamics NAV Server instance.

## SYNTAX

```
New-NAVServerInstance -ManagementServicesPort <ServicePort> [-ClientServicesPort <ServicePort>]
 [-SOAPServicesPort <ServicePort>] [-ODataServicesPort <ServicePort>] [-DeveloperServicesPort <ServicePort>]
 [-DatabaseServer <DatabaseServer>] [-DatabaseInstance <DatabaseInstance>] [-DatabaseName <DatabaseName>]
 [-Multitenant] [-DatabaseCredentials <PSCredential>] [-ClientServicesCredentialType <String>]
 [-ServicesCertificateThumbprint <ClientServicesCertificateThumbprint>] [-ServiceAccount <ServiceAccount>]
 [-ServiceAccountCredential <PSCredential>] [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the New-NAVServerInstance cmdlet to create a new Microsoft Dynamics NAV Server instance.
You must specify a name for the instance, in addition to values for the four port parameters.
All other configuration values for the new instance are based on default values.

Make sure that you verify the DatabaseServer and DatabaseName values after the instance is created, to ensure that the instance can accept client requests. All permissions that are required for the instance to start are configured automatically.

## EXAMPLES

### EXAMPLE 1
```
New-NAVServerInstance NewInstance -ManagementServicesPort 8099 -ClientServicesPort 8100 -SOAPServicesPort 8101 -ODataServicesPort 8102 -verbose

VERBOSE: NavCommand.BeginProcessing
VERBOSE: NavCommand.ProcessRecord
VERBOSE: Creating Instance directory C:\Program Files\Microsoft Dynamics NAV\80\Service\Instances\NewNAVServer
VERBOSE: Adding Windows Firewall (and UrlAcl) rules for Server Instance MicrosoftDynamicsNavServer$NewNAVServer
VERBOSE: Adding Windows Firewall (and UrlAcl) rules for Server Instance MicrosoftDynamicsNavServer$NewNAVServer
VERBOSE: Adding Windows Firewall (and UrlAcl) rules for Server Instance MicrosoftDynamicsNavServer$NewNAVServer
VERBOSE: NavCommand.EndProcessing
```

This example creates a new Microsoft Dynamics NAV Server instance.
It configures the necessary firewall exceptions and performs the necessary Access Control List registrations.

### EXAMPLE 2
```
Get-Credential | New-NAVServerInstance NewInstance -ServiceAccount User -ManagementServicesPort 8099 -ClientServicesPort 8100 -SOAPServicesPort 8101 -ODataServicesPort 8102 -verbose

VERBOSE: NavCommand.BeginProcessing
VERBOSE: NavCommand.ProcessRecord
VERBOSE: Performing operation "New-NAVServerInstance" on Target "ServerInstance = MicrosoftDynamicsNavServer$NewInstance, DatabaseInstance = ".
VERBOSE: Creating Instance directory C:\Program Files\Microsoft DynamicsNAV\80\Service\Instances\NewInstance
VERBOSE: Installing Server Instance MicrosoftDynamicsNavServer$NewInstance
VERBOSE: Setting service parameter: 'ManagementServicesPort' to value: '8099'
VERBOSE: Setting service parameter: 'ClientServicesPort' to value: '8100'
VERBOSE: Setting service parameter: 'SOAPServicesPort' to value: '8101'
VERBOSE: Setting service parameter: 'ODataServicesPort' to value: '8102'
VERBOSE: NavCommand.EndProcessing
```

This example prompts for ServiceAccount credentials and then creates a new Microsoft Dynamics NAV Server instance.

## PARAMETERS

### -ClientServicesCredentialType
The type of client credential used for client authentication.
Possible values are: Windows, Username, NavUserPassword and AccessControlService.

If you use the Windows credential type, then the client connects with current user.
This user must be known to both the server and the client.
This is the default credential type.
Typically, it is used on a LAN with Active Directory.
With the Windows credential type, X.509 certificates are not used.

If you use the UserName credential type, then the user must specify username/password credentials on the client.
These credentials are then validated against Windows authentication by Microsoft Dynamics NAV Server.
There must already be a corresponding user in Windows.
Security certificates are required to protect the passing of credentials across a wide-area network.
This setting should typically be used when the computer on which Microsoft Dynamics NAV Server is installed is part of an authenticating Active Directory domain but the computer where the client is installed is not part of the domain.

If you use the NavUserPassword credential type, then authentication is managed by Microsoft Dynamics NAV Server but is not based on Windows users or Active Directory.
The user is prompted for username/password credentials when they start the client.
The credentials are then validated by an external mechanism.
Security certificates are required to protect the passing of credentials.
This mode is intended for hosted environments, for example, where Microsoft Dynamics NAV is implemented in Windows Azure and the list of allowed users is maintained by Microsoft Dynamics NAV and not based on Windows users.

If you use the AccessControlService credential type, then authentication is handled by Windows Azure AccessControlService (ACS) or Microsoft Azure Active Directory (Microsoft Azure AD) for user authentication services.
You can use only the security token types that are supported by ACS, namely, SAML 1.1, SAML 2.0.
and SWT.
With this credential setting enabled, SOAP and OData Services accept a user-mapped ServiceSecurityToken as authentication model.
This credential type is used by Windows Azure Marketplace.

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

### -ClientServicesPort
Specifies the listening TCP port for clients such as Microsoft Dynamics NAV Windows client and Microsoft Dynamics NAV Web client.

```yaml
Type: ServicePort
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseCredentials
The user name and password of the login account that the Microsoft Dynamics NAV Server instance will use to connect to the Microsoft Dynamics NAV database in SQL Server.
This parameter configures the Microsoft Dynamics NAV Server instance to use SQL Server Authentication instead of Windows Authentication on the connection to the database.
If the Microsoft Dynamics NAV Server instance is configured for multitenancy, then parameter configure SQL Authentication on the connection to the application database, not the tenant database.

The login account must be a member of the db_owner role on the database.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseInstance
Specifies the SQL Server instance on which the Microsoft Dynamics NAV database is installed.

```yaml
Type: DatabaseInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the Microsoft Dynamics NAV database.

```yaml
Type: DatabaseName
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseServer
Specifies the name of the computer on which the SQL Server instance for the Microsoft Dynamics NAV database is installed.

```yaml
Type: DatabaseServer
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagementServicesPort
Specifies the TCP port that is used to manage the Microsoft Dynamics NAV Server instance.
The Management Services port has no exceptions in the firewall, and will only be accessed from the local computer. The port is used by Windows PowerShell for access Microsoft Dynamics NAV Server management data.

```yaml
Type: ServicePort
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Multitenant
Specifies the Microsoft Dynamics NAV Server instance to be a multitenant instance.

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

### -ODataServicesPort
Specifies the listening HTTP port for Microsoft Dynamics NAV OData web services.

```yaml
Type: ServicePort
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.You must use single-quotes around the instance name.

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

### -ServiceAccount
Specifies the Windows-based computer account that the Microsoft Dynamics NAV Server instance must use to log on.
The default value is NT AUTHORITY\NETWORK SERVICE.
Only NetworkService and User values are supported.
This parameter accepts values from the enum System.ServiceProcess.ServiceAccount.

```yaml
Type: ServiceAccount
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceAccountCredential
Specifies a set of security credentials that you must use when configuring the service account.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServicesCertificateThumbprint
Specifies the certificate thumbprint for the x509 certificate that is going to be used for securing communication with the server.

The certificate must be stored in the local machine store and in the personal sub-store in the certificate store.

The private key of the certificate must be present and exchangeable.

The certificate must be in .pfx format, not .cer format.

The certificate can be either self-signed or issued by a trusted certification authority (CA).

When specifying a ServicesCertificateThumbprint, SOAP web services and OData web services become HTTPS.

```yaml
Type: ClientServicesCertificateThumbprint
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SOAPServicesPort
Specifies the listening HTTP port for Microsoft Dynamics NAV SOAP web services.

```yaml
Type: ServicePort
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -DeveloperServicesPort
Specifies the listening HTTP port for Dynamics NAV Developer web services.

```yaml
Type: ServicePort
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## System.String
You can pipe a string that contains a Dynamics NAV Server instance name or the security credentials to the cmdlet.

## OUTPUTS

### None

## NOTES
## RELATED LINKS

[Get-NAVServerInstance](Get-NAVServerInstance.md)

[Remove-NAVServerInstance](Remove-NAVServerInstance.md)

[Set-NAVServerInstance](Set-NAVServerInstance.md)

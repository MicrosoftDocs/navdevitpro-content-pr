---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-NAVWebServerInstance

## SYNOPSIS
Creates a new Microsoft Dynamics NAV Web Server instance and binds this instance to a Microsoft Dynamics NAV Server instance.

## SYNTAX

```
New-NAVWebServerInstance [-ClientServicesCredentialType <NavClientCredentialType>]
 [-ClientServicesPort <ServicePort>] [-RegionFormat <LanguageSetting>] [-Language <LanguageSetting>]
 [-Company <String>] [-DnsIdentity <String>] -Server <String> -ServerInstance <String>
 [-WebServerInstance] <String> [-AcsUri <String>] [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the New-NAVWebServerInstance cmdlet to create a new Microsoft Dynamics NAV Web Server instance for the Microsoft Dynamics NAV Web client and bind this instance to a Microsoft Dynamics NAV Server instance on the same computer or on a remote computer.
In IIS, a new virtual directory and application for the instance is added to the existing Microsoft Dynamics NAV 2016 Web Client website.
If you call this cmdlet multiple times then multiple instances are created.
For more information, see How to: Set Up Multiple Web Server Instances for the Microsoft Dynamics NAV Web Client in the Microsoft Dynamics NAV Developer and IT Pro Help in the MSDN Library.

## EXAMPLES

### EXAMPLE 1
```
New-NAVWebServerInstance MyNavApp -Server MyNavServer -ServerInstance DynamicsNAV -Company MyNavCompany
```

Description

-----------

This example creates a new Microsoft Dynamics NAV Web Server instance that is named MyNavApp.
The Microsoft Dynamics NAV Server instance connects to the DynamicsNAV server instance on the MyNavServer computer.
By default, the Microsoft Dynamics NAV Server instance is configured to use Windows authentication to authenticate users.

## PARAMETERS

### -AcsUri
Specifies the Uniform Resource Identifier (URI) of Windows Azure Access Control Service (ACS) or Windows Azure Active Directory (AAD) that is used for authenticating Microsoft Dynamics NAV users.
This parameter is only relevant when the ClientServicesCredentialType parameter is set to AccessControlService.
With AccessControlService, users are authenticated by using either Windows Azure Access Control Service (ACS) or Windows Azure Active Directory (AAD).
When using ACS authentication, the ACSUri parameter specifies the URI of the ACS login page for relying party applications.
An example of a URI is https://CRONUSInternationalLtd.accesscontrol.windows.net/v2/wsfederation?wa=wsignin1.0%26wtrealm=https%3a%2f%2flocalhost%2f.
For more information, see For more information about ACS, see How to: Configure the Microsoft Dynamics NAV Web Client for ACS in the Microsoft Dynamics NAV Developer and IT Pro Help in the MSDN Library.
When using AAD authentication, the ACSUri specifies the URI of the AAD authentication page, which is specific to an AAD tenant for signing on users.
An example of a URI is https://login.windows.net/\[Tenant_ID\]/wsfed?wa=wsignin1.0%26wtrealm=https%3a%2f%2flocalhost%2f.
\[Tenant_ID\] specifies the AAD tenant.
For more information, see Authenticate Users with Windows Azure Active Directory in the Microsoft Dynamics NAV Developer and IT Pro Help in the MSDN Library.

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

### -ClientServicesCredentialType
The type of client credential used for client authentication.
Possible values are: Windows, UserName, NavUserPassword, or AccessControlService.

```yaml
Type: NavClientCredentialType
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientServicesPort
Specifies the port that is used to communicate with the client services of the Microsoft Dynamics NAV Server instance.

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

### -Company
Specifies the name of the Microsoft Dynamics NAV company to connect to.

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

### -DnsIdentity
Identifies a certificate in the local certificate store that must be used when signing in to Microsoft Dynamics NAV Server.
One of the initial checks when a client authenticates a server is to compare the value of the Subject field of the certificate to the URI that is used to contact the service.
The DNS of both must match.
For example, if the URI of the service is "net.tcp://NavServer.com:7046/DynamicsNav/Service" then the Subject field of the certificate must also contain the value "NavServer.com".
Typically, the Subject is prefixed with "CN" (for common name), for example, "CN = NavServer.com", but it can also just be "NavServer.com".
It is also possible for the Subject field to be blank, in which case the validation rules will be applied to the Subject Alternative Name field of the certificate.
The DnsIdentity configuration settings can be used to associate an endpoint with the specified Dns name.
The DnsIdentity configuration settings can be used to associate an endpoint with the specified Dns name.

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

### -Language
Sets the language version of the Microsoft Dynamics NAV Web client.
The value must be a valid culture name for a language in Microsoft Dynamics NAV, such as en-US or da-DK.
The culture name has the format: nn-NN.
nn is a lowercase two-letter code for the language and NN is an uppercase two-letter code for the country or region.
For example, en-US is for English (United States) and en-GB is for English (United Kingdom), and da-DK is for Danish (Denmark).
There are some languages that use a three-letter language code or a suffix to the region code.
The culture name must follow the RFC 1766 standard.
For a list of the most common culture names, see http://go.microsoft.com/fwlink/?LinkID=255174.
For the Spanish version of Microsoft Dynamics NAV, you must set the value to es-ES_tradnl.

```yaml
Type: LanguageSetting
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RegionFormat
Specifies the culture name that is used to format dates, times, numbers, and currency in the Microsoft Dynamics NAV Web client.
A language culture name that has the format: nn-NN.
nn is a lowercase two-letter code for the language and NN is an uppercase two-letter code for the country or region.
For example, en-US is for English (United States), en-GB is for English (United Kingdom), and da-DK is for Danish (Denmark).
There are some languages that use a three-letter language code or a suffix to the region code.
The culture name must follow the RFC 1766 standard.
For a list of the most common culture names, see http://go.microsoft.com/fwlink/?LinkID=255174.

```yaml
Type: LanguageSetting
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
The name of the computer on which Microsoft Dynamics NAV Server is installed.
This parameter accepts "localhost" if the Microsoft Dynamics NAV Server instance and the Microsoft Dynamics NAV Web Server instance are installed on the same computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
The name of the instance of Microsoft Dynamics NAV Server that this instance of Microsoft Dynamics NAV Web Server connects to.

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

### -WebServerInstance
The name of the web server instance.
This will be used as the name of the IIS web application.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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


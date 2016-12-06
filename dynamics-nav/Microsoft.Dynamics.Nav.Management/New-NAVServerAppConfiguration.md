---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=827797
schema: 2.0.0
---

# New-NAVServerAppConfiguration

## SYNOPSIS
Creates a new application-specific configuration file for the Dynamics NAV Server instance.

## SYNTAX

```
New-NAVServerAppConfiguration -ApplicationId <String> -ServerInstance <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
You can have more than one application running on a single Dynamics NAV Server instance.
By default, the server instance will use the settings in the CustomSettings.config for all applications. This cmdlet enables you to create an additional configuration file that is only used by a specific application. The application-specific configuration file can be used to configure the following settings.

AppProtocolName - Specifies the protocol to use in URL links to the application, similar to the http protocol in web page links.
For example, with Dynamics 365 for Financials, by setting the parameter to "ms-financials"  means that "ms-financials:///?page=31" would open the items list page 31.

AppIdUri - Specifies the APP ID URI that is assigned to the Dynamics NAV application in Azure Active Directory (Azure AD).

AzureActiveDirectoryClientApplicationId - Specifies the CLIENT ID that is assigned to the Dynamics NAV application in Azure AD.

The application-specific file is saved in the same location as the CustomSettings.config file for the Dynamics NAV Server installation. For example, by default, the location is C:\Program Files\Microsoft Dynamics NAV\NN\Service, where NN is the server version number.

The generated configuration file does not contain any settings. To add settings, use the Set-NAVServerAppConfiguration cmdlet.

The application-specific configuration file is used to supplement the CustomSettings.config file of the server instance. The server instance will load the correct application-specific configuration file for an application based on the application ID that is specified by the ApplicationId parameter.

## EXAMPLES

### EXAMPLE 1
```
New-NAVServerAppConfiguration -ApplicationId FIN -ServerInstance DynamicsNAV
```

This example creates a new application-specific configuration file for the FIN application.
The generated file has the name CustomerSettings.FIN.config.

## PARAMETERS

### -ApplicationId
Specifies the identifier that is assigned to the application to create a configuration file for.
The value is used in the name of the new configuration file, which has the format: CustomSettings.ApplicationId.config.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

## OUTPUTS

## NOTES
## RELATED LINKS

[Get-NAVServerAppConfiguration](Get-NAVServerAppConfiguration.md)

[Set-NAVServerAppConfiguration](Set-NAVServerAppConfiguration.md)

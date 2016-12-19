---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=827798
schema: 2.0.0
---

# Set-NAVServerAppConfiguration

## SYNOPSIS
Specifies a setting in an application-specific configuration file for a Dynamics NAV Server instance.

## SYNTAX

```
Set-NAVServerAppConfiguration -ApplicationId <String> -KeyName <String> [-KeyValue <String>]
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
You can use this cmdlet to set a key-value pair for one of the following settings in an application-specific configuration file:  AppProtocolName, AppIdUri, and AzureActiveDirectoryClientApplicationId.

The application-specific configuration file must already exist on the Dynamics NAV Server installation.
You use the New-NAVServerAppConfiguration cmdlet to create the configuration file.
The settings that you add in the application-specific configuration file will be used by the server instance.

## EXAMPLES

### EXAMPLE 1
```
Set-NAVServerAppConfiguration -ServerInstance DynamicsNAV  -ApplicationId FIN -KeyName AppProtocolName
-KeyValue 'ms-financials'
```

Description

-----------

This example sets the AppProtocolName setting in the configuration file for the Dynamics 365 for Financials to ms-financials.

## PARAMETERS

### -ApplicationId
Specifies the application-specific configuration file for the Dynamics NAV Server instance that you want to modify.
The value corresponds to the ID of the application.
You can determine the ApplicationId from the name of the application-specific configuration file.
For example, if the file name is CustomSettings.FIN.config, then the ApplicationId is FIN.

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

### -KeyName
Specifies the name of the setting that you want to set in the configuration file.
The following settings are available:

AppProtocolName - Specifies the protocol to use in URL links to the application, similar to the http protocol in web page links. For example, with Dynamics 365 for Financials, by setting the parameter to "ms-financials"  means that "ms-financials:///?page=31" would open the items list page 31.
This parameter is used by the GETURL function on the server-side to produce the links when called from the application.

Currently, the supported values are: ms-financials and ms-dynamicsnav.

AppIdUri - Specifies the APP ID URI that is assigned to the Dynamics NAV application in Azure Active Directory (Azure AD).

AzureActiveDirectoryClientApplicationId - Specifies the CLIENT ID that is assigned to the Dynamics NAV application in Azure AD.

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

### -KeyValue
Specifies the value for the configuration setting that is defined by the KeyName parameter.

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

[New-NAVServerAppConfiguration](New-NAVServerAppConfiguration.md)

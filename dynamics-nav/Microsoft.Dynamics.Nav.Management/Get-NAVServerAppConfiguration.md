---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-NAVServerAppConfiguration

## SYNOPSIS
Returns the settings in an application-specific configuration file of a Dynamics NAV Server instance.

## SYNTAX

```
Get-NAVServerAppConfiguration -ApplicationId <String> -ServerInstance <String> [-Force]
```

## DESCRIPTION
The Get-NAVServerAppConfiguration cmdlet retrieves the settings in the application-specific configuration file.
You create an application-specific configuration file by using the New-NAVServerApplicationConfiguration cmdlet.

## EXAMPLES

### EXAMPLE 1
```
Get-NAVServerAppConfiguration -ServerInstance DynamicsNAV  -ApplicationId FIN
```

This example returns the settings in the application-specific configuration file for the FIN application.

## PARAMETERS

### -ApplicationId
Specifies the application-specific configuration file for the Dynamics NAV Server instance that you want to view.  The value corresponds to the ID of the application.
You can determine the ApplicationId from the name application-specific configuration file.
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

## OUTPUTS

### System.Xml.XmlNode
An XML document containing key value pairs of the application specific server configuration.

## NOTES
## RELATED LINKS
[New-NAVServerAppConfiguration](New-NAVServerAppConfiguration.md)

[Set-NAVServerAppConfiguration](Set-NAVServerAppConfiguration.md)

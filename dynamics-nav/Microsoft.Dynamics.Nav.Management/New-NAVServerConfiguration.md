---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-NAVServerConfiguration

## SYNOPSIS
Creates a new configuration with default values, or to replace the existing configuration for a Microsoft Dynamics NAV Server instance.

## SYNTAX

### DefaultServerSettingsDocument (Default)
```
New-NAVServerConfiguration [[-ServerInstance] <String>] [-Force] [-WhatIf] [-Confirm]
```

### NewServerSettingsDocument
```
New-NAVServerConfiguration [[-ServerInstance] <String>] [-ServerSettingsDocument <XmlNode>] [-Force] [-WhatIf]
 [-Confirm]
```

## DESCRIPTION
Use the New-NAVServerConfiguration cmdlet to create a new configuration with default values, or to replace the existing configuration for a Microsoft Dynamics NAV Server instance.
Use the New-NAVServerConfiguration cmdlet without arguments to create a new configuration with default values.
The cmdlet returns an XML document that contains default configuration settings for a Microsoft Dynamics NAV Server instance.
Use New-NAVServerConfiguration with the -ServerInstance and -ServerSettingsDocument parameters to replace the existing configuration for a Microsoft Dynamics NAV Server instance.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Set-NAVServerConfiguration MyInstance -KeyName DatabaseServer -KeyValue DatabaseServer.Domain.Com
```

Description

-----------

In this example, the Set-NAVServerConfiguration cmdlet sets the value for the appSettings Key 'DatabaseServer' to 'DatabaseServer.Domain.Com' for a Microsoft Dynamics NAV Server instance, MyInstance.

## PARAMETERS

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

If you specify a Dynamics NAV Server instance, the configuration replaces the current configuration for that instance.
A new CustomSettings.config file is created in the service directory for the instance, overwriting any existing CustomSettings.config file.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ServerSettingsDocument
Specifies the Dynamics NAV Server instance configuration document in XML format.
You cannot specify a ServerSettingsDocument unless you also specify a ServerInstance.
For more information, see Example 2.

```yaml
Type: XmlNode
Parameter Sets: NewServerSettingsDocument
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### System.Xml.XmlDocument

## NOTES
## RELATED LINKS


---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401394
schema: 2.0.0
---

# Set-NAVServerConfiguration

## SYNOPSIS
Configures settings for a Microsoft Dynamics NAV Server instance.

## SYNTAX

### KeyValuePairSettings (Default)
```
Set-NAVServerConfiguration -KeyName <String> [-KeyValue <String>] [-Element <String>]
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DatabaseCredentials
```
Set-NAVServerConfiguration -DatabaseCredentials <PSCredential> [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Use the Set-NAVServerConfiguration cmdlet to configure settings for a Microsoft Dynamics NAV Server instance. Values are written directly to the configuration file for the instance (CustomSettings.config). New setting values do not take effect until you restart the server instance.

## EXAMPLES

### EXAMPLE 1
```
Set-NAVServerConfiguration MyInstance -KeyName DatabaseServer -KeyValue DatabaseServer.Domain.Com
```

In this example, the Set-NAVServerConfiguration cmdlet sets the value for the 'DatabaseServer' key to 'DatabaseServer.Domain.Com' for a Microsoft Dynamics NAV Server instance, MyInstance.

## PARAMETERS

### -KeyName
The configuration key name.
Examine the CustomSettings.config file to determine the correct key name.

```yaml
Type: String
Parameter Sets: KeyValuePairSettings
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyValue
The configuration key value.
For more information about supported values, see "Configuring Microsoft Dynamics NAV Server" in the Microsoft Dynamics NAV Developer and IT Pro Help. A version of this topic is available online at: http://go.microsoft.com/fwlink/?LinkID=163750.

```yaml
Type: String
Parameter Sets: KeyValuePairSettings
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseCredentials
The user name and password of the login account that the Microsoft Dynamics NAV Server instance will use to connect to the Microsoft Dynamics NAV database in SQL Server.
This parameter is configures the Microsoft Dynamics NAV Server instance to use SQL Server Authentication instead of Windows Authentication on the connection to the database.
The login account must be a member of the db_owner role on the database.

```yaml
Type: PSCredential
Parameter Sets: DatabaseCredentials
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Element
Specifies the navigation path from the root element to the appSettings section of the configuration document.

```yaml
Type: String
Parameter Sets: KeyValuePairSettings
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

[Get-NAVServerConfiguration](Get-NAVServerConfiguration.md)

[New-NAVServerConfiguration](Set-NAVServerConfiguration.md)

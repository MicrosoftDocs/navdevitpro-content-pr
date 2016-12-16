---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=723206
schema: 2.0.0
---

# Import-NAVConfigurationPackageFile

## SYNOPSIS
Imports a configuration package file into the Microsoft Dynamics NAV application database.

## SYNTAX

```
Import-NAVConfigurationPackageFile [-Path] <String> [[-SetupType] <String>] [[-ProcessingOrder] <Int32>]
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Import-NAVConfigurationPackageFile cmdlet enables you to take a configuration package file and import it into the application database of Microsoft Dynamics NAV. After the package is imported it available to all tenants. From the Dynamics NAV client, you can then apply the package to specific new customers.

Set the -Force parameter to overwrite an existing package.

## EXAMPLES

### EXAMPLE 1
```
Import-NAVConfigurationPackageFile -Path C:\Documents\NAV9.00.W1.ENU.TRIAL.rapidstart -ServerInstance 'MyCompNAV'

None
```

This example imports the configuration package file that is called NAV9.00.W1.ENU.TRIAL.rapidstart. The file is located in the C:\Documents folder. It imports the contents as a Company setup type configuration package into the application database of the Dynamics NAV Server instance MyCompNAV.

### EXAMPLE 2
```
Get-NAVServerInstance | Import-NAVConfigurationPackageFile -Path MyPack.rapidstart -Type Other
```

Gets a list of all Dynamics NAV server instances on the computer, then takes the MyPack.rapidstart file from the current directory and imports it into the application  databases on the server instance.
The configuration package is imported as a type Other.

## PARAMETERS

### -Path
Specifies the folder path and file name to the configuration package file.
These files typically have a .rapidstart extension.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SetupType
Specifies the setup type or purpose of the configuration package file.
You can set this parameter to one of the following values:

Company -
Application -
Other -

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: Company
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProcessingOrder
Specifies the order in which the configuration packages will be processed.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: 0
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.  You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-NavConfigurationPackageFile](Remove-NavConfigurationPackageFile.md)

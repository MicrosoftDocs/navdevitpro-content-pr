---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=521784
schema: 2.0.0
---

# Set-NAVAddIn

## SYNOPSIS
Specifies the description, category, resource or resourcefile of an add-in that is registered in the system table 2000000069 Add-ins of the Microsoft Dynamics NAV database.

## SYNTAX

### AddInResource (Default)
```
Set-NAVAddIn -AddInName <String> [-Version <String>] -PublicKeyToken <String> [-Category <AddInCategory>]
 [-Description <String>] [-Resource <Byte[]>] [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AddInResourceFile
```
Set-NAVAddIn -AddInName <String> [-Version <String>] -PublicKeyToken <String> [-Category <AddInCategory>]
 [-Description <String>] [-ResourceFile <String>] [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Use this cmdlet to change the settings of an existing add-in the database.

## EXAMPLES

### EXAMPLE 1
```
Set-NAVAddIn -ServerInstance DynamicsNAV -AddinName MyNavAddin -PublicKeyToken 31bf3856ad364e35 -ResourceFile 'c:\addins\MyNavAddin.zip'
```

This example changes the MyNavAddin add-in that is registered in the system table 2000000069 Add-ins. The example specifies the add-in files that are contained in the MyNavAddin.zip file that is located in the folder path c:\addin, which can be used for automatic deployment of the add-in to the Microsoft Dynamics NAV Server and clients.

## PARAMETERS

### -AddInName
Specifies the name of the add-in that you want to change.

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

### -Version
Specifies a version number for the add-in.
The version number must have the format N.N.N.N, such as 8.0.0.0.
This version number must match the version number that is assigned to the assembly.

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

### -PublicKeyToken
Specifies a public token key of the add-in.
The public key token is a 16-character key that is given to the add-in assembly when it is built and signed in Microsoft Visual Studio.

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

### -Category
Specifies the category of the add-in.
There are four categories that you can specify: DotNet Control Add-in, DotNet Interoperability, Javascript Control Add-in, and Language Resource.

```yaml
Type: AddInCategory
Parameter Sets: (All)
Aliases: 
Accepted values: JavaScriptControlAddIn, DotNetControlAddIn, DotNetInteroperability, LanguageResource

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies a description of the add-in for identification purposes.

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

### -Resource
Specifies a resource file for the add-in.
the resource file can be used to stream the add-in to the Microsoft Dynamics NAV Server instance.

```yaml
Type: Byte[]
Parameter Sets: AddInResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceFile
Specifies the full path to a compressed file (.zip type) that contains the add-in assembly and associated files.
The full path includes the drive, folders and file name.
Use this parameter to set up the automatic deployment of the add-in files to Microsoft Dynamics NAV Server instances instead of manually deploying the files.

```yaml
Type: String
Parameter Sets: AddInResourceFile
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NAVAddIn](Get-NAVAddIn.md)

[New-NAVAddIn](New-NAVAddIn.md)

[Remove-NAVAddIn](Remove-NAVAddIn.md)

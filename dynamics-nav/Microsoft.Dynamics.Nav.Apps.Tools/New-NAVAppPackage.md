---
external help file: Microsoft.Dynamics.Nav.Apps.Tools.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=616078
schema: 2.0.0
---

# New-NAVAppPackage

## SYNOPSIS
Creates a NAV App package file (.navx) at the specified location based on the specified manifest file and source files.

## SYNTAX

```
New-NAVAppPackage [-Path] <String> [-Manifest] <NavAppManifest> [-SourcePath] <String[]> [[-Logo] <String>]
 [[-ScreenShots] <String[]>] [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Use the New-NAVAppPackage cmdlet to create a .navx package file to distribute a NAV App.
You can then use the package file to deploy the NAV App to a Microsoft Dynamics NAV Server instance.

## EXAMPLES

### Example 1
```
New-NavAppManifest -Name 'Proseware SmartApp' -Publisher 'Proseware, Inc.' -Version 2.3.4.500 | New-NAVAppPackage -Path 'C:\Proseware SmartApp.navx' -SourcePath 'C:\NavAppFiles'
```

This example creates a new NAV App package using new in-memory NAV App manifest metadata and the source files in the C:\NavAppFiles folder.

### Example 2
```
Get-NAVAppManifest -Path '.\Manifest-Proseware SmartApp.xml' | New-NAVAppPackage -Path 'C:\Proseware SmartApp.navx' -SourcePath 'C:\NavAppFiles'
```

This example creates a new NAV App package using the NAV App manifest file and source files in the C:\NavAppFiles folder.

### Example 3
```
Get-NAVAppManifest -Path '.\Manifest-Proseware SmartStuff.xml' | New-NAVAppPackage -Path 'C:\Proseware SmartStuff.navx' -SourcePath C:\NavAppFiles, 'C:\permissions.xml'
```

This example creates a new NAV App package using the NAV App manifest file and source files in the C:\NavAppFiles folder and an exported permission set file in the location provided.

### Example 4
```
Get-NAVAppManifest -Path '.\Manifest-Proseware SmartStuff.xml' | New-NAVAppPackage -Path 'C:\Proseware SmartStuff.navx' -SourcePath C:\NavAppFiles, 'C:\permissions.xml' -Logo C:\SmartLogo.png -ScreenShots C:\SmartScreenShots
```

This example creates a new NAV App package using the NAV App manifest file and source files in the C:\NavAppFiles folder, an exported permission set file in the location provided, a logo image in the location provided, and screen shot images files in the C:\SmartScreenShots folder.

## PARAMETERS

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

### -Force
Forces the command to run without asking for user confirmation to overwrite an existing package file at the given path.

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

### -Logo
Specifies the path to and image file to use as the logo when creating this Nav App package

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Manifest
Specifies the manifest object that contains the metadata that defines the NAV App package.
You can pass this object from the New-NAVAppManifest or Get-NAVAppManifest cmdlets to the New-NAVAppPackage cmdlet.

```yaml
Type: NavAppManifest
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns the path of the created package file.

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

### -Path
Specifies the file name and the location where the NAV App package file (.navx) must be placed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: OutputPath, Output

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScreenShots
Specifies the path(s) to the image and files, or a directory containing such, to include as product screen shots in the NAV App package.
Use a comma (,) to separate multiple paths.
(example: C:\NavAppImages\, C:\Images\ScreenShot.jpg)

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourcePath
Specifies the location of the delta files and full object files, or a folder that contains the files, that you want to include in the NAV App package.
Use a comma (,) to separate multiple paths as in the following example: C:\NavAppFiles\, C:\Permissions\PermissionSet.xml

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Get-NAVAppManifest](https://go.microsoft.com/fwlink/?linkid=616072)

[New-NAVAppManifest](https://go.microsoft.com/fwlink/?linkid=616071)

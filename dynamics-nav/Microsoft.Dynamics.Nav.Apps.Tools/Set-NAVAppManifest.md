---
external help file: Microsoft.Dynamics.Nav.Apps.Tools.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=616073
schema: 2.0.0
---

# Set-NAVAppManifest

## SYNOPSIS
Sets one or more available properties on an in-memory manifest.

## SYNTAX

```
Set-NAVAppManifest [-Manifest] <NavAppManifest> [-Id <Guid>] [-Name <String>] [-Publisher <String>]
 [-Brief <String>] [-Description <String>] [-Version <Version>] [-CompatibilityId <Version>]
 [-PrivacyStatement <String>] [-Eula <String>] [-Help <String>] [-Url <String>] [-Prerequisites <String[]>]
 [-Dependencies <String[]>]
```

## DESCRIPTION
Use the Set-NAVAppManifest cmdlet to set properties on an in-memory manifest object.
You can create the manifest object by using the New-NAVAppManifest cmdlet.
You can then write the updated manifest object to disk by using the New-NAVAppManifestFile cmdlet.
The manifest is required when creating the NAV App package file (.navx) using the New-NAVAppPackage cmdlet.

## EXAMPLES

### Example 1
```
New-NavAppManifest -Name "Proseware SmartApp" -Publisher "Proseware, Inc." -Description "First NAV App by Proseware" |
                    Set-NavAppManifest -Version 2.3.4.500 -CompatibilityId 2.0.0.0

                    AppId              : 16f55eab-44d2-4428-8550-040b63308e72
                    AppName            : Proseware SmartApp
                    AppPublisher       : Proseware, Inc.
                    AppDescription     : First NAV App by Proseware
                    AppBrief           :
                    AppVersion         : 2.3.4.500
                    AppCompatibilityId : 2.0.0.0
                    AppPrivacyStatement:
                    AppEula            :
                    AppHelp            :
                    AppUrl             :
                    AppLogo            :
                    AppScreenShots     :
                    Capabilities       : {}
                    Prerequisites      : {}
                    Dependencies       : {}
```

This example creates a new manifest with a few properties and then passes the created manifest to the Set-NAVAppManifest cmdlet in order to set the version and compatibilityId properties.

### Example 2
```
Get-NAVAppManifest -Path '.\Manifest-Proseware SmartApp.xml' | Set-NavAppManifest -Version 2.3.4.500 -CompatibilityId 2.0.0.0 | New-NavAppManifestFile -Path ".\Manifest-Proseware SmartApp.xml" -Force
```

This example gets a manifest from file, sets the version and compatibilityId properties and then saves the updated manifest back to file.
The -Force parameter overwrites the existing file.

## PARAMETERS

### -Manifest
Specifies the manifest object on which the properties are to be set by the cmdlet's parameter values.

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

### -Name
Specifies the name of the NAV App.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies the description for the NAV App.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
Specifies the version of the NAV App.
The version is a string in the format of Major.Minor.Build.Revision.
The value should be incremented for each new version of the NAV App.

```yaml
Type: Version
Parameter Sets: (All)
Aliases: AppVersion

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the unique identifier for the NAV App.
A unique identifier will be generated if a value is not provided.
The same unique identifier should be used for each new version of the NAV App.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: AppId

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Publisher
Specifies the publisher of the NAV App.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppPublisher

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompatibilityId
Specifies the compatibility ID of the NAV App.
The compatibility ID is a version string in the format of Major.Minor.Build.Revision.
The value is used to indicate whether there are compatibility related code changes between different versions of the NAV App.

```yaml
Type: Version
Parameter Sets: (All)
Aliases: AppCompatibilityId

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prerequisites
Specifies the objects that must exist in order to deploy the NAV App to a NAV server instance.
The prerequisites is a string in the format of type=ID, where type would include NAV object types like Table, CodeUnit, Page, etc.
Use a comma (,) to separate the prerequisites.
(example: Table=397, CodeUnit=78)

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dependencies
Specifies the path to a package file (.navx) for another NAV App that this NAV App is dependent on.
Use a comma (,) to separate the paths to multiple .navx files, such as in the following example: C:\Proseware\SmartAppBase.navx, C:\Proseware\ProsewareBase.navx

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Brief
Specifies the brief description for the NAV App.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppBrief

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Eula
Specifies a hyperlink to the NavApp End User License Agreement.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppEula

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Url
Specifies a generic hyperlink.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppUrl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrivacyStatement
Specifies a hyperlink to the NavApp Privacy Statement.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppPrivacyStatement

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Help
Specifies a hyperlink to the NavApp help site.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppHelp

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

[Get-NAVAppManifest](Get-NAVAppManifest.md)

[New-NAVAppManifest](New-NAVAppManifest.md)

---
external help file: Microsoft.Dynamics.Nav.Apps.Tools.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=616071
schema: 2.0.0
---

# New-NAVAppManifest

## SYNOPSIS
Creates a new in-memory manifest object with the specified NAV App metadata.

## SYNTAX

```
New-NAVAppManifest [-Name] <String> [-Publisher] <String> [[-Id] <Guid>] [[-Brief] <String>]
 [[-Description] <String>] [[-Version] <Version>] [[-CompatibilityId] <Version>] [[-PrivacyStatement] <String>]
 [[-Eula] <String>] [[-Help] <String>] [[-Url] <String>] [-Prerequisites <String[]>] [-Dependencies <String[]>]
```

## DESCRIPTION
Use the New-NAVAppManifest cmdlet to create a new in-memory manifest object that defines a NAV App along with its required prerequisites and dependencies.
The manifest object can then be written to disk using the New-NAVAppManifestFile cmdlet.
The manifest is required when creating the NAV App package file (.navx) using the New-NAVAppPackage cmdlet.
The manifest property values can be changed using the Set-NAVAppManifest cmdlet.

## EXAMPLES

### Example 1
```
New-NavAppManifest -Name "Proseware SmartApp" -Publisher "Proseware, Inc." -Description "First NAV App by Proseware"

                    AppId              : 384ed42e-534b-491f-9c4b-dfc8140bbc38
                    AppName            : Proseware SmartApp
                    AppPublisher       : Proseware, Inc.
                    AppDescription     : First NAV App by Proseware
                    AppBrief           :
                    AppVersion         : 1.0.0.0
                    AppCompatibilityId : 1.0.0.0
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

This example creates a new in-memory manifest object with the provided property values and defaults for properties not provided.

### Example 2
```
New-NavAppManifest -Name "Proseware SmartApp" -Publisher "Proseware, Inc." -Brief "First Proseware App" -Description "The first NAV App created by Proseware" -Version "2.3.4.500" -CompatibilityId "2.0.0.0" -Id 384ed42e-534b-491f-9c4b-dfc8140bbc38 -Dependencies C:\Proseware\SmartAppBase.navx, C:\Proseware\ProsewareBase.navx -Prerequisites Table=397, CodeUnit=78 -PrivacyStatement http://www.proseware.com/SmartApp/privacypolicy.aspx -Ula http://www.proseware.com/SmartApp/ULA.aspx -Help http://www.proseware.com/SmartApp/Support.aspx -Url http://www.proseware.com/SmartApp/

                    AppId              : 384ed42e-534b-491f-9c4b-dfc8140bbc38
                    AppName            : Proseware SmartApp
                    AppPublisher       : Proseware, Inc.
                    AppDescription     : First NAV App by Proseware
                    AppBrief           : First Proseware App
                    AppVersion         : 2.3.4.500
                    AppCompatibilityId : 2.0.0.0
                    AppPrivacyStatement: http://www.proseware.com/SmartApp/privacypolicy.aspx
                    AppEula            : http://www.proseware.com/SmartApp/ULA.aspx
                    AppHelp            : http://www.proseware.com/SmartApp/Support.aspx
                    AppUrl             : http://www.proseware.com/SmartApp/
                    AppLogo            :
                    AppScreenShot      :
                    Capabilities       : {}
                    Prerequisites      : {Table=397, CodeUnit=78}
                    Dependencies       : {SmartApp Base, Proseware Inc., 2.0.0.300, Proseware Base, Proseware Inc, 2.0.0.0}
```

This example creates a new in-memory manifest object with values provided for all properties.

### Example 3
```
New-NavAppManifest -Name "Proseware SmartApp" -Publisher "Proseware, Inc." -Description "First NAV App by Proseware" | New-NavAppManifestFile -Path ".\Manifest-Proseware SmartApp.xml"
```

This example uses New-NAVAPPManifestFile cmdlet to persist the new in-memory manifest to a file.
This can then be saved under source control for later use.

### Example 4
```
New-NAVAppManifest -Name "Proseware SmartApp" -Publisher "Proseware, Inc." -Description "First NAV App by Proseware" | New-NAVAppPackage -Path 'C:\Proseware SmartApp.navx' -SourcePath C:\NavAppFiles
```

This example shows how to pass the in-memory manifest to New-NAVAppPackage cmdlet to get a .navx file.

## PARAMETERS

### -Id
Specifies the unique identifier for the NAV App.
A unique identifier will be generated if a value is not provided.
The same unique identifier should be used for each new version of the NAV App.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: AppId

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Publisher
Specifies the publisher of the NAV App, such as your company name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppPublisher

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the NAV App.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies the description for the NAV App.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppDescription

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Version
Specifies the version of the NAV App.
The version is a string in the format of Major.Minor.Build.Revision, with a default value of 1.0.0.0 if not provided.
The value should be incremented for each new version of the NAV App.

```yaml
Type: Version
Parameter Sets: (All)
Aliases: AppVersion

Required: False
Position: 7
Default value: 1.0.0.0
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CompatibilityId
Specifies the compatibility ID of the NAV App.
The compatibility ID is a version string in the format of  Major.Minor.Build.Revision, with a default value of 1.0.0.0 if not provided.
The value is used to indicate whether there are compatibility related code changes between different versions of the NAV App.
If a new version of the NAV App does not break compatibility, leave the compatibility ID the same as the previous version.

```yaml
Type: Version
Parameter Sets: (All)
Aliases: AppCompatibilityId

Required: False
Position: 8
Default value: 1.0.0.0
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Dependencies
Specifies the path to a package file (.navx) for another NAV App that this NAV App is dependent on.
Use a comma (,) to separate the paths to multiple .navx files., such as in the following example: C:\Proseware\SmartAppBase.navx, C:\Proseware\ProsewareBase.navx

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Prerequisites
Specifies the objects that must exist in order to deploy the NAV App to a Microsoft Dynamics NAV server instance.
The prerequisites is a string in the format of type=ID, where type can be any NAV object type such as Table, CodeUnit, or Page.
Use a comma (,) to separate the prerequisites, such as in the following example: Table=397, CodeUnit=78

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Brief
Specifies the brief description for the NAV App.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppBrief

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrivacyStatement
Specifies a hyperlink to the NAV App Privacy Statement.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppPrivacyStatment

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Eula
Specifies a hyperlink to the NAV AppEnd User License Agreement.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppEula

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Url
Specifies a generic hyperlink.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppUrl

Required: False
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Help
Specifies a hyperlink to the NAV App help site.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AppHelp

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### NavAppManifest

## NOTES
## RELATED LINKS
[Get-NAVAppManifest](Get-NAVAppManifest.md)

[New-NavAppManifestFile](New-NAVAppManifestFile.md)  

[NEW-NAVAppPackage](New-NAVAppPackage.md)  

[Set-NAVAppManifest](Set-NAVAppManifest.md)

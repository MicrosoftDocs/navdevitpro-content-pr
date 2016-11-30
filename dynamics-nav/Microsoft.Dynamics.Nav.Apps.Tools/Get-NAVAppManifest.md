---
external help file: Microsoft.Dynamics.Nav.Apps.Tools.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-NAVAppManifest

## SYNOPSIS
Loads a manifest for an NAV App from an external source.

## SYNTAX

```
Get-NAVAppManifest [-Path] <String>
```

## DESCRIPTION
Use the Get-NAVAppManifest cmdlet to load a manifest from an NAV App from an external source, such as an .xml file.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-NAVAppManifest -Path '.\Manifest-Proseware SmartApp.xml'

                    AppId              : 3c88160c-e0eb-4fe1-b4f6-011e45d74b10
                    AppName            : Proseware SmartApp
                    AppPublisher       : Proseware, Inc.
                    AppDescription     : First NAV App by Proseware
                    AppVersion         : 2.3.4.500
                    AppCompatibilityId : 2.0.0.0
                    AppPrivacyStatement: http://www.proseware.com/SmartApp/privacypolicy.aspx
                    AppEula            : http://www.proseware.com/SmartApp/ULA.aspx
                    AppHelp            : http://www.proseware.com/SmartApp/Support.aspx
                    AppUrl             : http://www.proseware.com/SmartApp/
                    AppLogo            :
                    AppScreenShots     : {}
                    Capabilities       : {}
                    Prerequisites      : {}
                    Dependencies       : {}
```

Description

-----------

This example gets a NAV App manifest from an XML manifest file.

### -------------------------- EXAMPLE 2 --------------------------
```
Get-NAVAppManifest -Path '.\Manifest-Proseware SmartApp.xml' | New-NAVAppPackage -Path 'C:\Proseware SmartApp.navx' -SourcePath C:\NavAppFiles
```

Description

-----------

This example gets a NAV App manifest from an XML manifest file and then passes the manifest to the New-NAVAppPackage cmdlet to create a new NAV App package.

## PARAMETERS

### -Path
Specifies the path to a file with an NAV App manifest.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### NavAppManifest

## NOTES
## RELATED LINKS


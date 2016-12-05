---
external help file: Microsoft.Dynamics.Nav.Apps.Tools.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=616075
schema: 2.0.0
---

# Export-NAVAppPermissionSet

## SYNOPSIS
Exports the specified permission set(s) from a Microsoft Dynamics NAV database to a file.

## SYNTAX

```
Export-NAVAppPermissionSet -PermissionSetId <String[]> -Path <String> [-ServerInstance] <String> [-PassThru]
 [-Force]
```

## DESCRIPTION
Use the Export-NAVAppPermissionSet cmdlet to export a permission set (or multiple permission sets) from a Microsoft Dynamics NAV database to a file.

## EXAMPLES

### Example 1
```
Export-NAVAppPermissionSet -ServerInstance DynamicsNAV -Path '.\PermissionSet.xml' -PermissionSetId PSA-VIEW
```

This example exports the permission set with the ID "PSA-VIEW" in the database that is used by the DynamicsNAV server instance to the PermissionSet.xml file.

### Example 2
```
$PermissionSetFile=Export-NAVAppPermissionSet -ServerInstance DynamicsNAV -Path '.\PermissionSet.xml' -PermissionSetId PSA-VIEW -PassThru

          Mode             LastWriteTime            Length Name
          ----             -------------            ------ ----
          -a---            8/5/2017   11:47 AM         450 PermissionSet.xml
```

This example exports the permission set with the ID "PSA-VIEW" in the database that is used by the DynamicsNAV server instance to the PermissionSet.xml file, and then returns the location of the file to a variable.
The variable could then be used when creating a package.
(Example: Get-NAVAppManifest -Path '.\Manifest-Proseware SmartStuff.xml' | New-NAVAppPackage -Path 'C:\Proseware SmartStuff.navx' -SourcePath C:\NavExtensionFiles, $PermissionSetFile

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation to overwrite an existing permission set file at the given path.

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

### -PassThru
Returns the path to the permission set file.

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
Specifies the name and location of the file that the permissions set is exported to.

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

### -PermissionSetId
Specifies the permission set ID(s) that will be exported.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the Microsoft Dynamics NAV Server instance that the permission set will be exported from, such as DynamicsNAV.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
## RELATED LINKS

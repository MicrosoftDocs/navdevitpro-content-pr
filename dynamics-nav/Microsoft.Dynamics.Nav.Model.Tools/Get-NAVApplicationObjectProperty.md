---
external help file: Microsoft.Dynamics.Nav.Model.Tools.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=398888
schema: 2.0.0
---

# Get-NAVApplicationObjectProperty

## SYNOPSIS
Gets Microsoft Dynamics NAV application object properties from the specified application object text files.

## SYNTAX

```
Get-NAVApplicationObjectProperty [-Source] <String[]> [<CommonParameters>]
```

## DESCRIPTION
Use the Get-NAVApplicationObjectProperty cmdlet to extract the values of the Version List, Date, Time, or Modified properties.
You can then use the Set-NAVApplicationObjectProperty cmdlet to change the relevant property values.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NAVApplicationObjectProperty -Source .\SOURCE\COD1.txt
```

This example gets the value of the object properties from the COD1.txt file in the SOURCE folder.
The values of the properties are also shown.

## PARAMETERS

### -Source
Specifies the folder where the application objects are stored that you want to get the information from.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PSPath

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

[Set-NAVApplicationObjectProperty](Set-NAVApplicationObjectProperty.md)

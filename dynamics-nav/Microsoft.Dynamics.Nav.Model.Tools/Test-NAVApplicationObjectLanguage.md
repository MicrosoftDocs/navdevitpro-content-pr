---
external help file: Microsoft.Dynamics.Nav.Model.Tools.dll-Help.xml
online version: 
schema: 2.0.0
---

# Test-NAVApplicationObjectLanguage

## SYNOPSIS
Tests captions in Microsoft Dynamics NAV application objects to test to validate if they have translated strings for the specified languages.

## SYNTAX

```
Test-NAVApplicationObjectLanguage [-Source] <String[]> [-LanguageId] <String[]> [-PassThru]
```

## DESCRIPTION
Use the Test-NAVApplicationObjectLanguage cmdlet to validate captions in Microsoft Dynamics NAV application objects.
The cmdlet tests all multilanguage strings to verify if the objects have translated strings for the specified languages.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\>Test-NAVApplicationObjectLanguage -Source TAB14.TXT -LanguageId ESP
```

Description

-----------

This example tests the application object in the TAB14.txt file for captions in Spanish.
If nothing is returned, the object has captions in ESP.
If one or more captions in ESP are missing, a technical error is shown.

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\>Test-NAVApplicationObjectLanguage -Source .\RESULT\*.TXT -LanguageId DAN
```

Description

-----------

This example tests the application objects in the RESULT folder for captions in Danish.
If nothing is returned, the object has captions in DAN.
If one or more captions in DAN are missing, a technical error is shown.

### -------------------------- EXAMPLE 3 --------------------------
```
PS C:\>   Test-NAVApplicationObjectLanguage -Source TAB14.TXT -LanguageId ESP -ErrorAction Stop

          }

          catch

          {

          Write-Host "One or more translations are missing for the ESP language." -ForegroundColor Yellow

          }
```

Description

-----------

This example tests the application object in the TAB14.txt file for captions in Spanish.
If nothing is returned, the object has captions in ESP.
If one or more captions in ESP are missing, an error is shown with the text that you specified.

## PARAMETERS

### -LanguageId
Specifies the language or list of languages that you want to test for, such as "DEU".
If you do not set this parameter, all available languages are tested.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies if you want to return a collection of objects that describe the missing translations.

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

### -Source
Specifies the text file or folder that contains the Microsoft Dynamics NAV application objects that you want to test.
The cmdlet does not modify these text files.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS


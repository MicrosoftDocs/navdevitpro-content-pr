---
external help file: Microsoft.Dynamics.Nav.Apps.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Unpublish-NAVApp

## SYNOPSIS
Unpublishes a NAV App from the app catalog of the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

### Properties (Default)
```
Unpublish-NAVApp [-Name] <String> [[-Publisher] <String>] [[-Version] <Version>] [-ServerInstance] <String>
```

### Path
```
Unpublish-NAVApp [-Path] <String> [-ServerInstance] <String>
```

## DESCRIPTION
Use the Unpublish-NAVApp cmdlet to remove a NAV App from the app catalog of the specified Microsoft Dynamics NAV Server instance.
The NAV App cannot be unpublished if it is currently installed for a tenant of the specified Microsoft Dynamics NAV Server instance.

## EXAMPLES

### EXAMPLE 1
```
Unpublish-NAVApp -ServerInstance DynamicsNAV90 -Name 'Proseware SmartApp'
```

Description

-----------

This example removes the NAV App with the specified name from the DynamicsNAV90 server instance's app catalog.

### EXAMPLE 2
```
Get-NAVAppInfo -ServerInstance DynamicsNAV90 -Name 'Proseware SmartApp' -Version 2.3.4.500 | Unpublish-NAVApp
```

Description

-----------

This example removes the NAV App returned from the Get-NAVAppInfo cmdlet from the DynamicsNAV90 server instance's app catalog.

### EXAMPLE 3
```
Unpublish-NAVApp -ServerInstance DynamicsNAV90 -Path '.\Proseware SmartApp.navx'
```

Description

-----------

This example removes the NAV App at the provided path from the DynamicsNAV90 server instance's app catalog.

## PARAMETERS

### -Name
Specifies the name of the NAV App to be unpublished.

            The results must return only a single NAV App to successfully unpublished.

```yaml
Type: String
Parameter Sets: Properties
Aliases: 

Required: True
Position: 21
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path to a NAV App Package file that you want to unpublish.

```yaml
Type: String
Parameter Sets: Path
Aliases: 

Required: True
Position: 21
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Publisher
Specifies the publisher of the NAV App to be unpublished.

            The results must return only a single NAV App to successfully unpublish.

```yaml
Type: String
Parameter Sets: Properties
Aliases: 

Required: False
Position: 22
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the Microsoft Dynamics NAV Server instance that the NAV App will be unpublished from, such as DynamicsNAV90.

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

### -Version
Specifies the version of the NAV App to be unpublished.

            The results must return only a single NAV App to successfully unpublish.

```yaml
Type: Version
Parameter Sets: Properties
Aliases: 

Required: False
Position: 23
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES
## RELATED LINKS


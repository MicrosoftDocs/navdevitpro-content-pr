---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-NAVWebService

## SYNOPSIS
Gets a list of all web services that are created in the application on the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Get-NAVWebService [-ServerInstance] <String> [-Force]
```

## DESCRIPTION
Use the Get-NAVWebService cmdlet to see all web services that have been created in the application that is mounted against the specified Microsoft Dynamics NAV Server instance.

## EXAMPLES

### EXAMPLE 1
```
Get-NAVWebService DynamicsNAV

ObjectId            ObjectType          ServiceName         Published

--------            ----------          -----------         ---------

21                  Page                Customer            True

26                  Page                Vendor              True
```

Description

-----------

The example returns a table of the web services that have been created in the application that is mounted against the Microsoft Dynamics NAV Server instance DynamicsNAV.
The return data shows two web services.

## PARAMETERS

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

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

### -Force
{{Fill Force Description}}

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

## INPUTS

## OUTPUTS

## NOTES
## RELATED LINKS


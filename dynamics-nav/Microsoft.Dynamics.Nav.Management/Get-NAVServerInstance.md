---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-NAVServerInstance

## SYNOPSIS
Obtains service details for the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Get-NAVServerInstance [[-ServerInstance] <String>] [-AsXml] [-Force]
```

## DESCRIPTION
Use the Get-NAVServerInstance cmdlet to obtain service details for the specified Microsoft Dynamics NAV Server instance.
If no Microsoft Dynamics NAV Server instance is specified, then the cmdlet obtains service details for all Microsoft Dynamics NAV Server instances on the server computer.
The service details include the name of the instance (for example, MicrosoftDynamicsNavServer$DynamicsNAV), the display name (for example, Microsoft Dynamics NAV Server \[DynamicsNAV\]), the state of the instance (Running or Stopped), the Service Account (that is, the account that the Microsoft Dynamics NAV Server uses for its credentials), the Microsoft Dynamics NAV Server version (such as 7.0.33571.0), and whether the instance is the default Microsoft Dynamics NAV Server instance.

## EXAMPLES

### EXAMPLE 1
```
Get-NavServerInstance MyInstance

Name           : MicrosoftDynamicsNavServer$MyInstance
DisplayName    : Microsoft Dynamics NAV Server [MyInstance]
State          : Running
ServiceAccount : NT AUTHORITY\NETWORK SERVICE
Version        : 7.1.33544.0
Default        : False
```

Description

-----------

This example returns status information for the MyInstance Microsoft Dynamics NAV Server instance.

## PARAMETERS

### -AsXml
Formats the cmdlet output as an XML document.

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

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

### System.Object[]

## NOTES
## RELATED LINKS


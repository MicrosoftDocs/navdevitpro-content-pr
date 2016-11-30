---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-NAVWebService

## SYNOPSIS
Creates a new Microsoft Dynamics NAV web service.

## SYNTAX

```
New-NAVWebService -ObjectType <ObjectType> -ObjectId <Int32> -ServiceName <String> [-Published <Boolean>]
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the New-NAVWebService cmdlet to create and optionally publish web services that are based on Microsoft Dynamics NAV application objects.
You can see which web services have already been created by running the Get-NAVWebService cmdlet.
In a multitenant deployment of Microsoft Dynamics NAV, web services are created in the application database, and they apply to all tenants that are mounted against that Microsoft Dynamics NAV Server instance.

## EXAMPLES

### EXAMPLE 1
```
New-NAVWebService -ServerInstance DynamicsNAV -ServiceName Customer -ObjectType Page -ObjectId 21 -Published 1
```

Description

-----------

This example uses the New-NAVWebService cmdlet to create and publish a web service that is based on page 21, Customer Card.

## PARAMETERS

### -ObjectId
Specifies the ID of the object that you want to publish as a web service.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectType
Specifies the type of the object that you want to publish as a web service.
You can publish two types of web services from Microsoft Dynamics NAV objects:
--SOAP Web Services.
You can publish either Microsoft Dynamics NAV pages or codeunits as SOAP services.
--OData Web Services.
You can publish either pages or queries as OData services.
For more information, see "Overview of Microsoft Dynamics NAV Web Services" in the Developer and ITPro documentation for Microsoft Dynamics NAV 2016.

```yaml
Type: ObjectType
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Published
Specifies if the web service must be published immediately.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -ServiceName
Specifies the name of the web service.

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

### None

## NOTES
## RELATED LINKS


---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Invoke-NAVCodeunit

## SYNOPSIS
Invokes the specified codeunit with the specified parameters.

## SYNTAX

```
Invoke-NAVCodeunit [-Tenant <TenantId>] [-CompanyName <String>] -CodeunitId <Int32> [-MethodName <String>]
 [-Argument <String>] [-Language <LanguageSetting>] [-TimeZone <InvokeCodeunitTimeZone>]
 [-ServerInstance] <String> [-Force]
```

## DESCRIPTION
You must specify a codeunit and a Microsoft Dynamics NAV Server instance.
Optionally, you can specify other parameters.
By default, the OnRun trigger is called, but you can specify a different method name and pass it an optional string argument.
You can run the codeunit within the scope of a company, a tenant, or both.
Optionally, you can specify the language that you want to use when you invoke the codeunit.
Return values are ignored.

## EXAMPLES

### EXAMPLE 1
```
Invoke-NAVCodeunit -ServerInstance DynamicsNAV -CompanyName 'CRONUS International Ltd.' -CodeunitId 100000 -Language 'da-DK'
```

Description

-----------

This example invokes codeunit 100000 and calls the OnRun trigger because no other method is specified.
The code runs with Danish language settings in the CRONUS International Ltd.
company in the Microsoft Dynamics NAV Server instance DynamicsNAV.

### EXAMPLE 2
```
Invoke-NAVCodeunit -ServerInstance DynamicsNAV -Tenant Tenant1 -CompanyName MyCompanyName -CodeunitId 2
```

Description

-----------

The example invokes codeunit 2, which initializes the MyCompanyName company.

### EXAMPLE 3
```
Invoke-NAVCodeunit -ServerInstance DynamicsNAV -Tenant Tenant1 -CompanyName MyCompanyName -CodeunitId 104048 -MethodName "UpgradeStep2"
```

Description

-----------

The example runs the UpgradeStep2 method in codeunit 104048, which is part of the Upgrade Toolkit for Microsoft Dynamics NAV.

## PARAMETERS

### -Argument
Specifies a string argument that is passed to the specified method on the codeunit.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CodeunitId
Specifies the ID of the codeunit that you want to invoke.
Specifies the ID of the codeunit that you want to invoke.
The Invoke-NAVCodeunit cmdlet calls the OnRun trigger in the specified codeunit.
You can call another method if you specify it in the MethodName parameter.

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

### -CompanyName
Specifies the name of the company that you want to run the codeunit in.
If you do not set this parameter, the codeunit will run in the default company for the Microsoft Dynamics NAV Server instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Language
Specifies the language that the codeunit will run in.
You must specify a valid culture name for a language in Microsoft Dynamics NAV, such as en-US or da-DK.
If the specified language does not exist on the Microsoft Dynamics NAV Server instance, the codeunit will run in en-US.

```yaml
Type: LanguageSetting
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MethodName
Specifies the method that will be called.
If no method is specified, the OnRun trigger is called.

```yaml
Type: String
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

### -Tenant
Specifies the ID of the tenant that you want to invoke the codeunit in, such as Tenant1.
This parameter is required unless the specified service instance is not configured to run multiple tenants.

```yaml
Type: TenantId
Parameter Sets: (All)
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -TimeZone
Specifies the time zone that the invoked codeunit will use for date calculations.
You can set the parameter to the following values: 

Utc - Uses Universal Coordinated Time (UTC) as the time zone.
This is the default value.
If you do not set this parameter, then UTC is used.

ClientTimezone - Uses the time zone that is configured for the computer on which the cmdlet is run. 

TenantTimezone - Uses the default time zone that is configured for the tenant.
The tenant's time zone is configured when the tenant is mounted on the Microsoft Dynamics NAV Server instance.
This is only relevant when the Microsoft Dynamics NAV Server instance is configured as a multitenant instance.

ServicesDefaultTimeZone - Uses the default time zone that is configured web services on the Microsoft Dynamics NAV Server instance.

```yaml
Type: InvokeCodeunitTimeZone
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


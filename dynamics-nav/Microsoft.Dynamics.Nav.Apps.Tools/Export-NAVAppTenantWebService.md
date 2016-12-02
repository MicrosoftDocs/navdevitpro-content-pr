---
external help file: Microsoft.Dynamics.Nav.Apps.Tools.dll-Help.xml
online version:
schema: 2.0.0
---

# Export-NAVAppTenantWebService

## SYNOPSIS
Exports the specified web service from a Microsoft Dynamics NAV database to a file.

## SYNTAX

```
Export-NAVAppTenantWebService -ServiceName <String> -ObjectType <String> -ObjectId <Int32> [-Tenant <TenantId>]
 -Path <String> [-ServerInstance] <String> [-PassThru] [-Force]
```

## DESCRIPTION
Use the Export-NAVAppTenantWebService cmdlet to export a web service from a Microsoft Dynamics NAV database to a file.

## EXAMPLES

### Example 1
```
Export-NAVAppTenantWebService -ServerInstance DynamicsNAV -Path .\TenantWebService.xml -ServiceName Customer -ObjectType Page -ObjectId 21
```

This example exports the web service with the name "Customer" on the Page 21 object in the database that is used by the DynamicsNAV server instance to the TenantWebService.xml file.

### Example 2
```
Export-NAVAppTenantWebService -ServerInstance DynamicsNAV -Path .\TenantWebService.xml -ServiceName Customer -ObjectType Page -ObjectId 21 -PassThru

          Mode             LastWriteTime            Length Name
          ----             -------------            ------ ----
          -a---            11/25/2017   11:47 AM         450 TenantWebService.xml
```

This example exports the web service with the name "Customer" on the Page 21 object in the database that is used by the DynamicsNAV server instance to the TenantWebService.xml file, then returns the location of the file.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation to overwrite an existing web service file at the given path.

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

### -ObjectId
Specifies the object ID of the web service that will be exported.

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
Specifies the object type of the web service that will be exported.

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

### -PassThru
Returns the path to the web service file.

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
Specifies the name and location of the file that the web service is exported to.

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

### -ServerInstance
Specifies the Microsoft Dynamics NAV Server instance that the web service will be exported from, such as DynamicsNAV.

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
Specifies the service name of the web service that will be exported.

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

### -Tenant
Specifies the tenant from which to export data.
If the server instance is configured for single tenant, do not set the parameter.

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

## INPUTS

## OUTPUTS

## NOTES
## RELATED LINKS

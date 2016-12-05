---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-NAVDataUpgrade

## SYNOPSIS
Gets information about a data upgrade process that is currently running, or the last completed data upgrade process.

## SYNTAX

### None (Default)
```
Get-NAVDataUpgrade [[-Tenant] <TenantId>] [-ServerInstance] <String> [-Force]
```

### ErrorOnly
```
Get-NAVDataUpgrade [[-Tenant] <TenantId>] [-ErrorOnly] [-ServerInstance] <String> [-Force]
```

### Detailed
```
Get-NAVDataUpgrade [[-Tenant] <TenantId>] [-Detailed] [-ServerInstance] <String> [-Force]
```

### Progress
```
Get-NAVDataUpgrade [[-Tenant] <TenantId>] [-Progress] [[-Interval] <Int32>] [-ServerInstance] <String> [-Force]
```

## DESCRIPTION
This information is available until the Microsoft Dynamics NAV Server instance is restarted.

## EXAMPLES

### EXAMPLE 1
```
Get-NAVDataUpgrade -ServerInstance DynamicsNAV

TenantId           : default


TotalFunctionCount : 3


ExecutedFunctions  : 3


Progress           : 100.00 %


Details            : {Check1, Upg1, Upg2}


Errors             :


State              : Completed
```

This example gets information about the data upgrade process that is currently running or the last completed data upgrade process.

### EXAMPLE 2
```
Get-NAVDataUpgrade -ServerInstance DynamicsNAV -Progress -Interval 2

Data Upgrade Process is currently in progress...


   Percent complete: 0.00 %


   [                                                                    ]
```

This example monitors progress of current data upgrade process by requesting the Microsoft Dynamics NAV Server for status every 2 seconds (the default is every second).

### EXAMPLE 3
```
Get-NAVDataUpgrade -ServerInstance DynamicsNAV -Details

SessionId    : 57


CodeunitId   : 111111


FunctionName : Check1


CompanyName  : CRONUS International Ltd.


StartTime    : 6/10/2014 5:45:37 PM


Duration     : 00:00:05.0008043


State        : Completed


Error        :


SessionId    : 58


CodeunitId   : 111111


FunctionName : Upg1


CompanyName  : CRONUS International Ltd.


StartTime    : 6/10/2014 5:45:42 PM


Duration     :


State        : FailedPendingResume


Error        : error.....


SessionId    : 59


CodeunitId   : 111111


FunctionName : Upg2


CompanyName  : CRONUS International Ltd.


StartTime    : 6/10/2014 5:45:42 PM


Duration     : 00:00:02.0071301


State        : Completed


Error        :
```

This example returns a detailed status of a currently running or completed data upgrade process.

## PARAMETERS

### -Detailed
Lists details about all the upgrade function that were invoked during the data upgrade process.
You can format the output as a table by appending the command with "| ft" or "| ogv".

```yaml
Type: SwitchParameter
Parameter Sets: Detailed
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ErrorOnly
Lists errors that occurred during the data upgrade process.

```yaml
Type: SwitchParameter
Parameter Sets: ErrorOnly
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Interval
Specifies how often (in seconds) the cmdlet requests the current status of data upgrade process. This parameter can only be used together with the -Progress switch.
The default value is 1 second.

```yaml
Type: Int32
Parameter Sets: Progress
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Progress
Provides live progress indication about the data upgrade process that is currently running.

```yaml
Type: SwitchParameter
Parameter Sets: Progress
Aliases:

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance. Include the name in single-quotes.

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
Specifies the ID of a tenant on the Microsoft Dynamics NAV Server instance.
You can omit the Tenant parameter only if the Microsoft Dynamics NAV Server instance is not configured to run multiple tenants.

```yaml
Type: TenantId
Parameter Sets: (All)
Aliases: Id

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### System.String
You can pass the value of the ServerInstance and Tenant parameters as a string to this cmdlet.

## OUTPUTS

### Microsoft.Dynamics.Nav.Types.NavUpgradeProcessExecutionDetails

## NOTES
## RELATED LINKS
[Resume-NAVDataUpgrade](Resume-NAVDataUpgrade.md)

[Start-NAVDataUpgrade](Start-NAVDataUpgrade.md)

[Stop-NAVDataUpgrade](Stop-NAVDataUpgrade.md)

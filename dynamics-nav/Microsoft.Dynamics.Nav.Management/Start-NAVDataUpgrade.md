---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Start-NAVDataUpgrade

## SYNOPSIS
Starts the process for upgrading the data in the tenant database.

## SYNTAX

```
Start-NAVDataUpgrade [[-Tenant] <TenantId>] [-Language <LanguageSetting>]
 [[-FunctionExecutionMode] <FunctionExecutionModeValue>] [-ContinueOnError] [-SkipCompanyInitialization]
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
The Start-NavDataUpgrade cmdlet calls the CheckPreconditions and Upgrade type functions in the upgrade codeunits that are set up for the application.
These functions are used to update data in tables of the tenant database when schema changes have been made to tables in application database. These functions are called as follows:

1. CheckPreconditions type functions are called (in random order).
If an error occurs, then any changes made in this step are rolled back.

2. Upgrade type functions are called (in random order).
If an error occurs, then any changes made in this step are rolled back.
All upgrade functions are executed in parallel (at the same time) unless you choose a different mode by setting the -FunctionExecutionMode parameter.
When running in parallel, it is important that all upgrade functions of the type "CheckPrecondition" and "Upgrade" can be run independently of each other.
If not, then place the dependent functions into a single upgrade function in the required order.
The progress of the running process can be monitored using Get-NAVDataUpgrade cmdlet, stopped using Stop-NAVDataUpgrade cmdlet, and resumed using Resume-NAVDataUpgrade cmdlet.

## EXAMPLES

### EXAMPLE 1
```
Start-NAVDataUpgrade -ServerInstance DynamicsNAV -Force
```

This example starts new data upgrade process that runs upgrade functions in parallel.

### EXAMPLE 2
```
Start-NAVDataUpgrade -ServerInstance DynamicsNAV -ContinueOnError -Force
```

This example starts new data upgrade process that runs upgrade functions run in parallel and is set to continue running when errors occur.

### EXAMPLE 3
```
Start-NAVDataUpgrade -ServerInstance DynamicsNAV -FunctionExecutionMode Serial -Force
```

This example starts new data upgrade process that runs upgrade functions in serial.
The execution of CheckPrecondition type functions will stop the process.
Failure in an upgrade function will suspend the upgrade process, which can then be resumed by using Resume-NAVDataUpgrade cmdlet.

## PARAMETERS

### -ContinueOnError
Specifies whether the Microsoft Dynamics NAV Server instance continues to execute other upgrade functions when an error occurs while executing an upgrade function.

If you do not set this parameter, then when an error occurs, the Microsoft Dynamics NAV Server instance will suspend the data upgrade process. It will cancel the execution of upgrade functions currently in progress and roll back any changes that were applied. Completed functions will not be rolled back.

The process remains in suspended state until you take one of the following actions:

- Fix the problems in the upgrade functions that failed, and then resume the process by using the Resume-NAVDataUpgrade cmdlet.
You should not add new upgrade functions at this time because they will be ignored when you resume the process.

- Stop the data upgrade process by using the Stop-NAVDataUpgrade cmdlet.
Stopping the process will not roll back changes made by upgrade functions that have already been executed.

If you set this parameter, then when an error occurs, the Microsoft Dynamics NAV Server instance will continue executing other upgrade functions.
At the end of the process, you can use the Get-NAVDataUpgrade cmdlet to see the list of failed upgrade functions. Changes that were applied by completed functions will not be rolled back.

When upgrading a large database, you should increase the SQL Command Timeout setting for the Microsoft Dynamics NAV Server instance that connects to the database to avoid timeouts during schema synchronization. The default setting is 30 minutes. For more information, see Configuring Microsoft Dynamics NAV Server in the MSDN Library.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FunctionExecutionMode
Specifies whether the Microsoft Dynamics NAV Server instance executes upgrade functions in series or parallel.

If the parameter is set to Serial, then CheckPrecondition and Upgrade type functions for each company are executed in series (one after another).

If the parameter is set to Parallel, then CheckPrecondition type functions will be executed for all companies in parallel (starting at the same time), and if completed successfully, then all Upgrade type functions for all companies will be executed in parallel.

```yaml
Type: FunctionExecutionModeValue
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.
You must include the name within single quotation marks.

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

### -SkipCompanyInitialization
Specifies not to run codeunit 2 Company Initialization during the data upgrade.

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

### -Tenant
Specifies the ID of the tenant that you want to synchronize with the application, such as Tenant1.
This parameter is required unless the specified service instance is not configured to run multiple tenants.

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

### -Language
Specifies the language version of Dynamics NAV on which to run the upgrade. The value must be a valid culture name for a language in Microsoft Dynamics NAV, such as en-US or da-DK. If the specified language does not exist on the Microsoft Dynamics NAV Server instance, the codeunit will run in en-US.

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

## INPUTS

### System.String
You can pass the value of the ServerInstance and Tenant parameters as a string to this cmdlet.

## OUTPUTS

## NOTES
Because the functions in the steps are called in random order, you should design the functions so that they are independent from each other.

## RELATED LINKS
[Get-NAVDataUpgrade](Get-NAVDataUpgrade.md)

[Resume-NAVDataUpgrade](Resume-NAVDataUpgrade.md)

[Stop-NAVDataUpgrade](Stop-NAVDataUpgrade.md)

---
external help file: Microsoft.Dynamics.Nav.Apps.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-NAVTableSynchSetupForDataUpgrade

## SYNOPSIS
Gets information about the tables that will be modified, added, or removed during a tenant data upgrade on the specified Microsoft Dynamics NAV Server instance for the specified tenant.

## SYNTAX

```
Get-NAVTableSynchSetupForDataUpgrade [-Tenant <String>] [-ServerInstance] <String>
```

## DESCRIPTION
Use the Get-NAVTableSynchSetupForDataUpgrade cmdlet to get information about tables that will be added, modified, or removed during a tenant data upgrade. 
The list of table changes is specific to the given tenant and will contain the unsynchronized changes between the tenant and application databases.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-NAVTableSynchSetupForDataUpgrade -ServerInstance DynamicsNAV91 -Tenant 'Tenant1'

          Old Table Id              : 4
          New Table Id              : 4
          Change Type               : Changed
          Base Hash                 : 45904077b849f7077fed7af69a44e949
          New Hash                  : 45904077b849f7077fed7af69a44e949
          Changes Affect SQL Schema : True
          Fields and Changes        : 6:The field does not exist anymore (It has been deleted or disabled)
          Indexes and Changes       : 0:The indexed fields have changed


          Old Table Id              : 0
          New Table Id              : 75001
          Change Type               : Missing
          Base Hash                 : 3a3f9a962bfeb0fc7a6d882946988e1f
          New Hash                  : 3a3f9a962bfeb0fc7a6d882946988e1f
          Changes Affect SQL Schema : False
          Fields and Changes        :
          Indexes and Changes       :
```

Description

-----------

This example returns the table modifications of a data upgrade for the tenant with the ID 'Tenant1' on the DynamicsNAV91 server instance.

## PARAMETERS

### -ServerInstance
Specifies the Microsoft Dynamics NAV Server instance, such as DynamicsNAV91.

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
Specifies the ID of the tenant who will be receiving the data upgrade, such as Tenant1.
Provide a value of 'default' if the specified server instance is not configured to run multiple tenants.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TenantId

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


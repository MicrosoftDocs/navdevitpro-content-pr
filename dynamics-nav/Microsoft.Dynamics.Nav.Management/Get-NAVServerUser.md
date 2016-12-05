---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-NAVServerUser

## SYNOPSIS
Returns information about all users created in the current Microsoft Dynamics NAV database.

## SYNTAX

```
Get-NAVServerUser [-Tenant <TenantId>] [-ServerInstance] <String> [-Force]
```

## DESCRIPTION
Use the Get-NAVServerUser cmdlet to return information about all users created in the current Microsoft Dynamics NAV database.
The following information is returned for each user:
                User Security ID
                User Name
                Full Name
                State
                Expiry Date
                Windows Security ID
                Change Password
                License Type
                AuthenticationEmail
                Password
                NameIdentifier
                AuthenticationKey
                WebServicesKey
                WebServicesKeyExpiryDate
                ProfileID
For more information about these values, see the Help for the User page in the Microsoft Dynamics NAV Windows client.

## EXAMPLES

### EXAMPLE 1
```
Get-NAVServerUser DynamicsNAV

 User Security ID         : b5013678-36e5-4469-8f07-dcc453fed66f
 User Name                : MyDomain_x005C_User1
 Full Name                : MyDomain_x005C_User1
 State                    : Enabled
 Expiry Date              : 1/1/0001 12:00:00 AM
 Windows Security ID      : S-1-5-21-xxxxxxxxxx-xxxxxxxxx-xxxxxxxxxx-xxxxxxx
 Change Password          : False
 License Type             : Full User
 AuthenticationEmail      :
 Password                 :
 NameIdentifier           :
 AuthenticationKey        :
 WebServicesKey           :
 WebServicesKeyExpiryDate : 1/1/0001 12:00:00 AM
 ProfileID                : BOOKKEEPER
```

Description

-----------

This example returns information about Microsoft Dynamics NAV users.

### EXAMPLE 2
```
Get-NAVServerUser DynamicsNAV90 -Tenant "Tenant1"

User Security ID         : b5013678-36e5-4469-8f07-dcc453fed66f
User Name                : MyDomain_x005C_User1
Full Name                : MyDomain_x005C_User1
State                    : Enabled
Expiry Date              : 1/1/0001 12:00:00 AM
Windows Security ID      : S-1-5-21-xxxxxxxxxx-xxxxxxxxx-xxxxxxxxxx-xxxxxxx
Change Password          : False
License Type             : Full User
AuthenticationEmail      :
Password                 :
NameIdentifier           :
AuthenticationKey        :
WebServicesKey           :
WebServicesKeyExpiryDate : 1/1/0001 12:00:00 AM
ProfileID                : BOOKKEEPER
```

Description

-----------

This example returns information about Microsoft Dynamics NAV users who belong to the tenant Tenant1 on the Microsoft Dynamics NAV Server instance.

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

### -Tenant
Specifies the ID of the tenant that the users are stored in, such as Tenant1.
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

## INPUTS

## OUTPUTS

### System.Data.DataRow

## NOTES
## RELATED LINKS


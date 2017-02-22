---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401359
schema: 2.0.0
---

# Get-NAVServerConfiguration

## SYNOPSIS
Returns configuration settings for the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Get-NAVServerConfiguration [-AsXml] [-ServerInstance] <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
Use the Get-NAVServerConfiguration cmdlet to return configuration settings for the specified Microsoft Dynamics NAV Server instance.

## EXAMPLES

### EXAMPLE 1
```
Get-NAVServerConfiguration MyInstance

key                                     value

---                                     -----

NetworkProtocol                         Default

DatabaseServer                          MyServer

DatabaseInstance                        NAVDEMO

DatabaseName                            My Database

EnableSqlConnectionEncryption           false

TrustSQLServerCertificate               false

ServerInstance                          MyInstance

ClientServicesPort                      7046

SOAPServicesPort                        7047

ODataServicesPort                       7048

ManagementServicesPort                  7045

ManagementServicesEnabled               true

ClientServicesEnabled                   true

SOAPServicesEnabled                     true

ODataServicesEnabled                    true

SOAPServicesSSLEnabled                  false

ODataServicesSSLEnabled                 false

PublicODataBaseUrl

PublicSOAPBaseUrl

PublicWebBaseUrl

PublicWinBaseUrl

DefaultClient                           Windows

SOAPServicesMaxMsgSize                  1024

ServicesUseNTLMAuthentication           false

ServicesDefaultTimeZone                 UTC

ServicesDefaultCompany

ODataServicesMaxPageSize                1000

ClientServicesOperationTimeout          MaxValue

ClientServicesProtectionLevel           EncryptAndSign

MaxConcurrentCalls                      40

ClientServicesMaxConcurrentConnections  150

ClientServicesReconnectPeriod           00:10:00

ClientServicesMaxNumberOfOrphanedCon... 20

ClientServicesCompressionThreshold      64

MetadataProviderCacheSize               150

ClientServicesMaxUploadSize             300

EnableDebugging                         false

DebuggingAllowed                        true

ClientServicesMaxItemsInObjectGraph     512

ClientServicesChunkSize                 28

ClientServicesProhibitedFileTypes       ade;adp;app;asp;bas;bat;chm;cmd;com;...

NASServicesStartupCodeunit

NASServicesStartupMethod

NASServicesStartupArgument

NASServicesEnableDebugging              false

NASServicesRetryAttemptsPerDay          3

ClientServicesCredentialType            Windows

UIElementRemovalOption                  LicenseFileAndUserPermissions

ClientServicesTokenSigningKey

ClientServicesFederationMetadataLoca...

AppIdUri

ServicesCertificateThumbprint

ServicesCertificateValidationEnabled    true

EnableSoftwareQualityMetrics            false

DataCacheSize                           9

SessionEventTableRetainPeriod           3

SqlCommandTimeout                       00:30:00

BufferedInsertEnabled                   true

DocumentServicesProvider                SHAREPOINTONLINE

EnableFullALFunctionTracing             false

Multitenant                             False

CloseInactiveSqlConnectionsGeneration   10

EnableALServerFileAccess                true

EnableStaticAssemblies                  False

ClientServicesIdleClientTimeout         MaxValue

OrphanedConnectionPurgePeriod           00:01:00

Binding

UseQueryForFind                         False

SqlParametersByOrdinal                  True

SqlConnectionTimeout                    0:01:30

SessionEventTablePurgeLookupPeriod      24:00:00

CacheSynchronizationPeriod              0:00:30

HeartbeatPeriod                         0:00:30

ResultSetGroupCacheUsesGlobalCache      True

UseCalculatedFieldsCache                True

UseResultSetCache                       True

EnableTempTableSizeReporting            False
```

This example returns configuration details for the Microsoft Dynamics NAV Server instance server named MyInstance on the Microsoft Dynamics NAV Server computer.

### EXAMPLE 2
```
(Get-NAVServerConfiguration MyInstance -AsXml).configuration.appSettings | fc

class XmlElement
{
add =
[
class XmlElement
{
key = NetworkProtocol
value = Default
}
class XmlElement
{
key = DatabaseServer
value = DB112
}
class XmlElement
{
key = DatabaseInstance
value = NAVDEMO
}
class XmlElement
{
key = DatabaseName
value = My Database
}
...
]

}
```

This example returns configuration details for the Microsoft Dynamics NAV Server instance named MyInstance on the Microsoft Dynamics NAV Server computer in XML format.

### EXAMPLE 3
```
Get-NAVServerConfiguration MyInstance -AsXml | fc

class XmlDocument
{
xml = version="1.0" encoding="utf-8"
configuration =
class XmlElement
{
configSections =
class XmlElement
{
section =
class XmlElement
{
name = uri
type = System.Configuration.UriSection, System, Version=4.0.0.0,
Culture=neutral, PublicKeyToken=b77a5c561934e089
}
}
appSettings =
class XmlElement
{
add =
[
class XmlElement
{
key = NetworkProtocol
value = Default
}
class XmlElement
{
key = DatabaseServer
value = DB112
}
class XmlElement
{
key = DatabaseInstance
value = NAVDEMO
}
class XmlElement
{
key = DatabaseName
value = My Database
}
...
]

}
system.diagnostics =
class XmlElement
{
assert =
class XmlElement
{
assertuienabled = false
}
}
uri =
class XmlElement
{
schemeSettings =
class XmlElement
{
add =
[
class XmlElement
{
name = http
genericUriParserOptions = DontUnescapePathDotsAndSlashes
}
class XmlElement
{
name = https
genericUriParserOptions = DontUnescapePathDotsAndSlashes
}
]

}
}
system.net =
class XmlElement
{
settings =
class XmlElement
{
httpListener =
class XmlElement
{
unescapeRequestUrl = false
}
}
}
runtime =
class XmlElement
{
gcConcurrent =
class XmlElement
{
enabled = false
}
gcServer =
class XmlElement
{
enabled = true
}
}
}
}
```

This example returns an XML document that contains the details for the Microsoft Dynamics NAV Server instance named MyInstance on the Microsoft Dynamics NAV Server computer.

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

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
You can pipe a string that contains a Microsoft Dynamics NAV Server instance name to the cmdlet.

## OUTPUTS

### System.Xml.XPathNodeList
Returns the configuration settings as well-formatted text.

### System.Xml.XmlDocument
If you use the AsXml parameter, then the cmdlet returns the configuration settings as an XML document.

## NOTES

## RELATED LINKS

[New-NAVServerConfiguration](New-NAVServerConfiguration.md)

[Set-NAVServerConfiguration](Set-NAVServerConfiguration.md)

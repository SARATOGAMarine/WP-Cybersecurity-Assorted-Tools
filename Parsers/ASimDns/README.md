# Azure Sentinel Information Model (ASIM) DNS parsers 

This template deploys all ASIM DNS parsers. The template is part of the Azure Sentinel Information Mode (ASIM).

The Azure Sentinel Information Mode (ASIM) enables you to use and create source-agnostic content, simplifying your analysis of the data in your Azure Sentinel workspace.

For more information, see:

- [Normalization and the Azure Sentinel Information Model (ASIM)](https://aka.ms/AzSentinelNormalization)
- [Azure Sentinel DNS normalization schema reference](https://aka.ms/AzSentinelDnsDoc)

<br>

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://aka.ms/AzSentinelDnsARM)

<br>

The template deploys the following:
* ASimDns - Source agnostic DNS events parser
* ASimDnsMicrosoftOMS - DNS Events from Microsoft OMS
* ASimDnsCiscoUmbrella - DNS Events from Cisco Umbrella
* ASimDnsInfobloxNIOS - DNS Events from Infoblox NIOS 
* vimDnsEmpty - Emtpy ASIM DNS table

Parametered Parsers:
* imDns - Source agnostic DNS events parser
* vimDnsMicrosoftOMS - DNS Events from Microsoft OMS
* vimDnsCiscoUmbrella - DNS Events from Cisco Umbrella
* vimDnsInfobloxNIOS - DNS Events from Infoblox NIOS 
Supported parameters: [parameters are optional]

| Name     | Type      | Default value |
|----------|-----------|---------------|
| starttime|  datetime | datetime(null)|
|  endtime |  datetime | datetime(null) |
|  srcipaddr |  string | '*' |
|  domain_has_any|  dynamic | dynamic([]) |
|  responsecodename |  string | '*' |
|  dnsresponsename |  string | '*' |
|  response_has_any|  dynamic| dynamic([])|
|  eventtype|  string | 'lookup' |


Note: the template asks for the list of Infoblox computers. You can ignore this input if you do not use Infoblox.  

<br>

## Version History

<br>

| Version | Date | Notes |
|---------|-----------|------|
| 0.1.0 | June 2021 | Initial release |
| 0.1.1 | July 2021 | Update to better align with OSSEM. The following field names where changed and the original left as an alias:<br> - Query -> DnsQuery<br> - QueryType -> DnsQueryType<br> - QueryTypeName -> DnsQueryTypeName<br> - ResponseName -> DnsResponseName<br> - ResponseCodeName -> DnsResponseCodeName<br> - ResponseCode -> DnsResponseCode<br> - QueryClass -> DnsQueryClass<br> - QueryClassName -> DnsQueryClassName<br> - Flags -> DnsFlags |


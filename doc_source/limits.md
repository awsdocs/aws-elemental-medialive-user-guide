# Quotas in AWS Elemental MediaLive<a name="limits"></a>

There are quotas \(formerly referred to as limits\) that apply to the resources and operations of AWS Elemental MediaLive\. A *quota* is a resource or operation cap that you can increase\. MediaLive also includes *constraints* that you can't change\. For more information about these constraints, see [AWS Elemental MediaLive feature rules and limits](eml-limitations-and-rules.md)\.

**Note**  
There is a limit on the number of actions that a channel schedule can contain\. This limit isn't listed here because it's not a quota that you can change\. This schedule actions limit is documented in [AWS Elemental MediaLive feature rules and limits](eml-limitations-and-rules.md)\.

The Service Quotas console provides information about MediaLive quotas\. Use the Service Quotas console to view default quotas and [request quota increases](https://console.aws.amazon.com/servicequotas/home?region=us-east-1#!/services/AWS Elemental MediaLivequotas) for AWS Elemental MediaLive\.

The following table describes the quotas for MediaLive\. 


****  

|  Resource or operation  |  Default quota  |  Comments  | 
| --- | --- | --- | 
| Channels | 5 | The maximum number of channels that you can create in this account in the current Region\. | 
| Channels with HEVC outputs | 5 | The maximum number of HEVC channels \(channels that include one or more HEVC outputs\) that you can create in this account in the current Region\. | 
| Channels with UHD outputs | 1 | The maximum number of UHD channels \(channels that include a UHD output\) that you can create in this account in the current Region\.For information about the maximum number of UHD outputs in these channels, see [AWS Elemental MediaLive feature rules and limits](eml-limitations-and-rules.md)\. | 
| Channels with CDI inputs | 2 | The maximum number of CDI channels \(channels that include one or more CDI inputs\) that you can create in this account in the current Region\. | 
| Inputs of type push \(not including VPC push inputs\) |  5  |  The maximum number of push inputs \(not including VPC push inputs\) that you can create in this account in the current Region\.  | 
| Inputs of type pull |  100  |  The maximum number of pull inputs that you can create in this account in the current Region\.  | 
| Inputs of type VPC push | 50 | The maximum number of VPC push inputs that you can create in this account in the current Region\. | 
| Inputs of type Elemental Link | 100 | The maximum number of Elemental Link inputs that you can create in this account in the current Region\. | 
| Input security groups | 5 | The maximum number of input security groups that you can create in this account in the current Region\. | 
| Multiplexes | 2 | The maximum number of channels that you can create in the current Region in this account in the current Region\. | 
| Reservations | 50 | The maximum number of reservations that you can create in this account in the current Region\. | 
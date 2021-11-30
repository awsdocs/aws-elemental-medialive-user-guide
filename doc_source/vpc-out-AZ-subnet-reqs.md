# Identifying subnet and Availability Zone requirements<a name="vpc-out-AZ-subnet-reqs"></a>

Subnets and Availability Zones apply as follows:
+ **Inputs **– Some MediaLive input types are in your VPC, which means that they are in a specific subnet\. For example, an RTMP input can be in your VPC\. For more information, see [Supported input formats and protocols](inputs-supported-formats.md)\.
+ **Endpoints** – The channel endpoints are in a subnet\. 
+ **Destinations** –The IP addresses for outputs in the VPC are in a subnet\. You identify IP addresses \(and their implied subnets\) when you [plan the downstream system](setting-up-downstream-system.md)\.

You must identify the VPCs and subnets for the MediaLive endpoints and for those of your output destinations that are an address in your VPC\. You must consider the following:
+ You must make sure that the setup follows the rules for allocation across subnets and across Availability Zones\. See [Use case A – no VPC inputs](vpc-out-caseA.md) and the section that follows it\.
+ Each subnet must have a private CIDR block \(a range of IP addresses\)\.
+ Each subnet must have at least two unused addresses in that block\. 

**Topics**
+ [Use case A – no VPC inputs](vpc-out-caseA.md)
+ [Use case B – channel includes VPC inputs](vpc-out-caseB.md)
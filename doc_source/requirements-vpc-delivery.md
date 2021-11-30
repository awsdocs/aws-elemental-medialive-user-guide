# Requirements for Amazon Elastic Compute Cloud—delivery via VPC<a name="requirements-vpc-delivery"></a>

Your deployment might include setting up some channels for delivery to output endpoints in Amazon Virtual Private Cloud \(Amazon VPC\)\. 

When a user sets up for this feature on the MediaLive console, they have the option to choose subnets, security groups, and EIPs from a dropdown list\. For the dropdown list to be populated with the resources in Amazon VPC, the user must have the appropriate permissions\. For information about this feature, see [Delivering outputs via your VPC](delivery-out-vpc.md)\.

The following table shows the actions in IAM that relate to access for populating the dropdowns\.


| Permissions | Service name in IAM | Actions | 
| --- | --- | --- | 
| View the VPC subnets and VPC security groups on the MediaLive console\. | EC2 | DescribeSubnets`DescribeSecurityGroups` | 
| View the Elastic IP addresses on the console\. The console finds the Elastic IP addresses that have been allocated for use in your AWS account\. | EC2 | DescribeAddresses | 
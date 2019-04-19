# Requirements for Amazon Elastic Compute Cloud—VPC Inputs<a name="requirements-for-vpc-input"></a>

Your deployment might include push inputs that connect to MediaLive from a VPC that you created with Amazon VPC\. 

When a user creates this type of input on the MediaLive console, they have the option to choose the subnet and security group from a dropdown list\. For the dropdown list to be populated with the resources in Amazon VPC, the user must have the appropriate permissions\. For more information about Amazon VPC inputs, see [Creating an Input](create-input.md)\.

The following table shows the actions in IAM that relate to access for populating the dropdown\.


| Permissions | Service Name in IAM | Actions | 
| --- | --- | --- | 
| View the VPC subnets and VPC security groups on the MediaLive console | EC2 | DescribeSubnets`DescribeSecurityGroups` | 
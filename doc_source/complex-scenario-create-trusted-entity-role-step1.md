# Step 1: Determine the Access Requirements<a name="complex-scenario-create-trusted-entity-role-step1"></a>

This requirements analysis must be performed by a person in your organization who understands your organization's requirements for access to resources\. This person must understand whether there is a requirement that MediaLive channels should be restricted in their access to resources in other AWS services\. For example, this person should determine whether channels should be restricted in their access to containers in MediaStore so that a specified channel can access some containers and not others\.

You must identify the services that MediaLive will interact with in your deployment\. Then within each service, you must identify the operations and resources that MediaLive needs access to\.

**To determine the access requirements for MediaLive**

1. See the table at the bottom of this section for information about the services that MediaLive typically needs access to\. Determine which of those services your deployment uses and which operations it needs\.

1. Within a service, determine the number of policies that you need to create\. Do you need several different combinations of objects and operations for different workflows, and do you need to keep those combinations separate from each for security reasons? 

   Specifically, determine whether you need access to different resources for different workflows, and whether it's important to restrict access to specific resources\. For example, in AWS Systems Manager Parameter Store you might have passwords that belong to different workflows, and you might want to allow only specific users to access the passwords for any given workflow\.

   If different workflows have different requirements for objects, operations, and resources, then for that service you need separate policies for each workflow\. 

   After you perform this analysis, you might determine that you need three different policies for MediaStore, four different policies for Amazon S3, and three policies for AWS Systems Manager Parameter Store\. 

1. Design each policy: identify the allowed \(or not allowed\) objects, operations, and the allowed \(or not allowed\) resources in the policy\. 

1. Determine if any of the policies that you have identified are covered by a managed policy\. 

1. For each workflow, identify the policies that you need for all the services that the workflow uses\.

   For example, for one workflow, you might need policy X for MediaStore, policy A for Amazon S3, and policy 1 for AWS Systems Manager Parameter Store\. For the second workflow, you might need policy Y for MediaStore, policy B for Amazon S3, and policy 1 for AWS Systems Manager Parameter Store\. For the third workflow, you need the same policies as for the first workflow\. 

1. Identify the number of roles that you need\. You need one role for each unique combination of policies\. Following our example, you need two roles: one role for the first and third workflows, and another for the second workflow\.

1. Assign names to all the policies and roles that you have identified\. Take care not to include sensitive identifying information \(such as a customer account name\) in these names\. 

## Summary Of Requirements for the MediaLive Trusted Entity<a name="trusted-entity-requirements"></a>

The following table lists the services that are often used in MediaLive deployment\. The third column specifies whether MediaLive itself needs access to these services\. If yes, then the fourth column suggests an existing policy that provides the required access, or else lists the operations and resources that you would typically include in a custom policy\.


****  

| Service | Tasks | Type of Access Required | Suggested Actions or Policy | 
| --- | --- | --- | --- | 
| AWS Elemental MediaLive  | Working with MediaLive features\. | MediaLive doesn't need access to itself\. Only the users need access\. |  | 
| AWS CloudTrail | Capturing MediaLive activity\. | MediaLive doesn't need IAM access for this task\. |  | 
| CloudWatch  | Displaying CloudWatch metrics information on the console, to monitor channel health\. | MediaLive doesn't need IAM access for this task\. Only the users need access\. |  | 
|  CloudWatch Events and Amazon SNS   | Setting up email notification so that users can be notified about MediaLive alerts that are sent to CloudWatch Events\. | MediaLive doesn't need access for this task\. Only the users need access\. |  | 
| CloudWatch Logs | Sending channel log information to CloudWatch Logs when a channel is running\. | When the channel is running, MediaLive must be able to send log messages to CloudWatch Logs\. |  `CreateLogGroup` `CreateLogStream` `PutLogEvents` `PutMetricFilter` `PutRetentionPolicy` `DescribeLogStreams` `DescribeLogGroups` And these resources:  `arn:aws:logs:`\*  `arn:aws:log-group:`\*  | 
| Amazon EC2 | Creating an RTP VPC input or RTMP VPC push input\. | When the user is creating a VPC input, MediaLive must have write access to Amazon EC2 in order to create network interfaces for the input\. |  `CreateNetworkInterface` `CreateNetworkInterfacePermission` `DescribeNetworkInterfaces` `DescribeSecurityGroup` `DescribeSubnets`  | 
|  | Deleting an RTP VPC input or RTMP VPC push input\. | When the user deletes a VPC input, MediaLive must have write access to Amazon Elastic Compute Cloud in order to delete the network interfaces for the input\. |  `DeleteNetworkInterface` `DeleteNetworkInterfacePermission` `DescribeNetworkInterfaces` `DescribeSubnets`  | 
| AWS Elemental MediaConnect | Creating an AWS Elemental MediaConnect input\. | When the user creates an MediaConnect input, MediaLive must have read/write access to the AWS Elemental MediaConnect flow, in order to add an output to that flow\. | ManagedDescribeFlow`ManagedAddOutput`To include these actions that start with "Managed" in a policy, you must view the policy in the **JSON** tab and enter the names of the actions\. You can't use the **visual editor** to choose these actions\.  | 
|  | Deleting an AWS Elemental MediaConnect input\. | When the user creates an AWS Elemental MediaConnect input, MediaLive should have read/write access to the AWS Elemental MediaConnect flow, in order to delete the outputs on the flow, because the outputs are no longer needed\. | ManagedDescribeFlow`ManagedDeleteOutput`To include these actions that start with "Managed" in a policy, you must view the policy in the **JSON** tab and enter the names of the actions\. You can't use the **visual editor** to choose these actions\.  | 
| AWS Elemental MediaPackage | Sending channel output to MediaPackage when a channel is running, if your deployment uses this service\. | When the user creates a MediaPackage output group, MediaLive must have read access to the AWS Elemental MediaPackage channel, in order to obtain the credentials required to send to that channel\. | DescribeChannel | 
| AWS Elemental MediaStore | Sending and retrieving assets from a MediaStore container when a channel is running, if your deployment uses this service\. | When the channel is running, MediaLive must have read access \(for a source\) or read/write access \(for a destination\)\. |  `ListContainers` `DescribeObject` `PutObject` `GetObject` `DeleteObject`  | 
| Resource Group Tagging | Attaching tags when creating resources—channels, inputs, and input security groups—and revising tags on existing resources\. | MediaLive doesn't need IAM access for this task\. Only the users need access\. |  | 
| Amazon S3 | Sending and retrieving assets from an Amazon S3 bucket when a channel is running, if your deployment uses this service\. | When the channel is running, MediaLive must have read access \(for a source\) or read/write access \(for a destination\) to the buckets\. |  `ListBucket` `PutObject` `GetObject` `DeleteObject`  | 
| AWS Systems Manager | Creating a password parameter on the MediaLive console\. | MediaLive doesn't need IAM access for this task\. Only the users need access\. |  | 
|  | Using a password parameter in the channel configuration\. See [Requirements for AWS Systems Manager—Creating Password Parameters in Parameter Store ](requirements-for-EC2.md)\. | When the channel is running, MediaLive must have read access to the AWS Systems Manager Parameter Store\. | The managed policy AmazonSSMReadOnlyAccess | 
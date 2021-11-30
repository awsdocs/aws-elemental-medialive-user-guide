# How VPC delivery works<a name="vpc-out-how-it-works"></a>

VPC delivery applies to each MediaLive channel\. You can have some channels that deliver via your VPC, and other channels that deliver in the regular way\.

With VPC delivery, the endpoints for the channel are in your VPC, rather than in the VPC that MediaLive owns\. This setup provides benefits including improved security, because the output doesn't have to go to the boundary of the public internet to reach the output destinations that are in your VPC\.

The following diagram illustrates how VPC delivery works\. The blue box is a channel with two pipelines\. The orange box is your VPC\. Notice that the endpoints for the two pipelines are in your VPC\. In this example, you have only one output group, with a destination in EC2 in your VPC\. This output group might be an HLS output group being sent to an HTTP server on your EC2 instance\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\vpc-delivery-overview.png)

The following diagram illustrates a channel with three output groups: 
+ The destination for one output group is on your EC2 instance\. 
+ The destination for the output shown at the top is on MediaPackage\. The output leaves the pipeline endpoint, goes to the boundary of AWS \(the gray box\), and comes back in, to the destination on AWS Elemental MediaPackage\.
+ The destination for the output shown at the bottom is on the public internet\. The output leaves the pipeline, then leaves AWS and enters the public internet\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\vpc-delivery-overview-multi-outputs.png)

You set up for delivery to your VPC as follows:
+ Identify subnets and security groups in your VPC for the channel endpoints\.
+ Identify subnets and security groups for the output destinations, for those outputs groups with destinations in your VPC\.
+ Determine if you need to identify Elastic IP addresses to associate with the channel\.
+ Check the permissions that are required for your trusted entity role for MediaLive\. You must update the role if your channel uses a custom trusted entity role, rather than the built\-in MediaLiveAccessRole role that is available through the console\. For more information, see [Reference: summary of requirements for the MediaLive trusted entity](trusted-entity-requirements.md)\.
+ Update the IAM policies for users\. For more information, see [Reference: summary of non\-administrator user access requirements](setup-users-step-1-summary.md)\.
+ When you create a channel, you must include this subnet, security group, and Elastic IP address information in the channel configuration\.

The following sections describe this setup in detail\.
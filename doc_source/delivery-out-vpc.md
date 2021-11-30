# Delivering outputs via your VPC<a name="delivery-out-vpc"></a>

You can set up a channel to have output endpoints in Amazon Virtual Private Cloud \(Amazon VPC\)\. This delivery mode is useful if an important output destination for your channel is an address in your VPC\.

The output destination in your VPC is typically an address in Amazon EC2\. It could also be a bucket in Amazon Simple Storage Service \(Amazon S3\), if you have set up VPC endpoints for Amazon S3\. You might want to send output to your VPC so that you can perform post\-processing, or so that you can deliver the video over AWS Direct Connect\. 

If you don't have a VPC, you can stop reading this section\. You will always set up the channel in the regular way, with endpoints in MediaLive\. You don't have to perform any special setup in order to set up channels in the regular way\.

## Rules and constraints<a name="vpc-out-rules"></a>

The following rules apply to a channel that is set up for delivery via your VPC:
+ You can't change an existing channel to either start delivering to your VPC or stop delivering via your VPC\.
+ The [channel class](plan-redundancy-mode.md) can be either standard or single\-pipeline\.
+ You can't change the channel class on an existing channel\.
+ You can't include multiplex output groups in the channel\.
+ The channel can have output groups with destinations in your VPC, with destinations at other locations \(such as AWS Elemental MediaPackage\), and with destinations on the public internet\.

**Note**  
The information in this section assumes that you are very familiar with Amazon Virtual Private Cloud, with AWS PrivateLink, with AWS Direct Connect, and with general networking practices\. 

**Topics**
+ [Rules and constraints](#vpc-out-rules)
+ [How VPC delivery works](vpc-out-how-it-works.md)
+ [Getting ready](vpc-out-get-ready-subnets.md)
+ [Setting up for VPC delivery](vpc-out-setup-steps.md)
+ [Changing the setup](vpc-out-change.md)
+ [Identifying subnet and Availability Zone requirements](vpc-out-AZ-subnet-reqs.md)
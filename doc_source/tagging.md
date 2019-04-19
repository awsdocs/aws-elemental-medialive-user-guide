# Tagging AWS Elemental MediaLive Resources<a name="tagging"></a>

A *tag* is a metadata label that you assign or that AWS assigns to an AWS resource\. Each tag consists of a *key* and a *value*\. For tags that you assign, you define the key and value\. For example, you might define the key as `stage` and the value for one resource as `test`\.

Tags help you do the following:
+ Identify and organize your AWS resources\. Many AWS services support tagging, so you can assign the same tag to resources from different services to indicate that the resources are related\. For example, you could assign the same tag to an AWS Elemental MediaLive channel and an endpoint that you assign to an AWS Elemental MediaTailor configuration\.
+ Track your AWS costs\. You activate these tags on the AWS Billing and Cost Management dashboard\. AWS uses the tags to categorize your costs and deliver a monthly cost allocation report to you\. For more information, see [Use Cost Allocation Tags](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html) in the [AWS Billing and Cost Management User Guide](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)\.

For tips on using tags, see the [AWS Tagging Strategies](https://aws.amazon.com/answers/account-management/aws-tagging-strategies/) post on the *AWS Answers* blog\. 

The following sections provide more information about tags for AWS Elemental MediaLive\.

## Supported Resources in AWS Elemental MediaLive<a name="supported-resources"></a>

The following resources in AWS Elemental MediaLive support tagging: 
+ Channels
+ Inputs
+ Input security groups

For information about adding and managing tags, see [Managing Tags](#tagging-add-edit-delete)\.

## Tag Restrictions<a name="tagging-restrictions"></a>

The following basic restrictions apply to tags on AWS Elemental MediaLive resources:
+ Maximum number of tags that you can assign to a resource – 50 
+ Maximum key length – 128 Unicode characters 
+ Maximum value length – 256 Unicode characters 
+ Valid characters for key and value – a\-z, A\-Z, 0\-9, space, and the following characters: \_ \. : / = \+ \- and @
+ Keys and values are case sensitive
+ Don't use `aws:` as a prefix for keys; it's reserved for AWS use

Additionally, AWS Elemental MediaLive doesn't support the tag\-based access control feature of AWS Identity and Access Management \(IAM\)\. 

## Managing Tags<a name="tagging-add-edit-delete"></a>

Tags are made up of the `Key` and `Value` properties on a resource\. 

You can use the AWS Management Console to manage tags\. You can also use the AWS Elemental MediaLive console, the AWS CLI, or the AWS Elemental MediaLive API to add, edit, or delete the values for these properties\. 

### Tagging Using the AWS Management Console<a name="tagging-management-console"></a>

We recommend that you manage tags by using the Tag Editor on the AWS Management Console\. The Tag Editor provides a central, unified way to create and manage your tags\. The Tag Editor provides the best results, including consistency between tags within MediaLive and between MediaLive and other services\. 

For more information, see [Working with Tag Editor](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/tag-editor.html) in [Getting Started with the AWS Management Console](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/getting-started.html)\.

### Tagging Using MediaLive<a name="tagging-medialive-console"></a>

For information about managing tags using the MediaLive console, see the following:
+ [Step 1: Complete the Channel and Input Details](creating-a-channel-step1.md) – for information about including tags when you create a channel
+ [Editing and Deleting a Channel](editing-deleting-channel.md) – for information about modifying tags in an existing channel
+ [Working with Inputs in AWS Elemental MediaLive](creating-input.md) – for information about including tags in an input
+ [Working with Input Security Groups](working-with-input-security-groups.md) – for information about including tags in an input security group

For information about managing tags using the AWS Elemental MediaLive API, see the following:
+ [Resources](https://docs.aws.amazon.com/mediapackage/latest/apireference/resources.html) in the *AWS Elemental MediaLive API Reference*
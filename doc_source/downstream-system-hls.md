# Setting Up the Downstream System for an HLS Output<a name="downstream-system-hls"></a>

If you want to deliver HLS output, you must decide if you want to create an HLS output group or a MediaPackage output group\. If you choose to create an HLS output group, you must set up the downstream system\.

## Choosing between HLS and MediaPackage Output Groups<a name="hls-vs-emp"></a>

For most output destinations, you create an HLS output in order to deliver HLS output\.

But if your destination is a channel in AWS Elemental MediaPackage, you can choose to create an HLS output or a MediaPackage output\. There are differences in the setup of each type:
+ When you decided on the [channel class](https://docs.aws.amazon.com/medialive/latest/ug/plan-redundancy-mode.html), you decided whether you wanted a standard channel \(to support input redundancy in AWS Elemental MediaPackage\) or a single\-pipeline channel\. If you chose single\-pipeline, then you should create an HLS output group because you will be able to control the [behavior when output is lost](hls-group-fields.md#hls-group-fields.title)\. 
+ The MediaPackage output requires less setup\. AWS Elemental MediaLive is already set up with most of the information that it needs to package and deliver the output to the AWS Elemental MediaPackage channel that you specify\.
+ For a MediaPackage output, the MediaLive channel and the AWS Elemental MediaPackage channel must be in the same AWS region\. For an HLS output, the two channels can be in different Regions \(although we recommend that they are in the same Region\)\.
+ In a MediaPackage output, the output is always a live stream, not a VOD stream\. In an HLS output, you can choose whether to create a live or a VOD stream\.
+ In a MediaPackage output, there are some restrictions on setting up ID3 metadata\. For details, see [Working with ID3 Metadata](id3-metadata.md)\.

To set up a MediaPackage output, see [Setting Up the Downstream System for a MediaPackage Output](downstream-system-emp.md)\.

## Setting up for an HLS Output<a name="hls-setup-downstream-system"></a>

In your downstream system, set up two inputs\.


| Downstream System | Setup | 
| --- |--- |
|  A CDN that uses HTTP \(or HTTPS\) `PUT`  | Set up the CDN so that the CDN expects MediaLive output at two inputs, one for each MediaLive channel pipeline\. Make a note of the input addresses, and of the input user name and input password, if applicable\.  | 
| A CDN that uses HTTP or HTTPS WebDAV | 
| An Akamai CDN \(this always uses HTTP or HTTPS\) | 
| AWS Elemental MediaPackage, serving as an origin server that a CDN such as Amazon CloudFront can pull from |  Create one AWS Elemental MediaPackage channel\. See [Creating a Channel](https://docs.aws.amazon.com/mediapackage/latest/ug/channels-create.html) in the *AWS Elemental MediaPackage User Guide*\.  Then view the details of the MediaPackage channel\. See [Viewing Channel Details](https://docs.aws.amazon.com/mediapackage/latest/ug/channels-view.html) in the *AWS Elemental MediaPackage User Guide*\. Make a note of the two input URLs, the input user names, and the input passwords\.  | 
|  An AWS Elemental MediaStore container, serving as an origin server that a CDN such as Amazon CloudFront can pull from  | Create two containers, one for each MediaLive channel pipeline\. Make a note of the full paths of the containers and the data plane values of the containers\. | 
| An Amazon S3 bucket, serving as an origin server that a CDN such as Amazon CloudFront can pull from |  Create two buckets, one for each MediaLive channel pipeline\. Make a note of the full paths of the buckets\.   | 
# Setting Up the Downstream System for a MediaPackage Output<a name="downstream-system-emp"></a>

A MediaPackage output is an HLS output where the destination is always a channel in AWS Elemental MediaPackage\. AWS Elemental MediaPackage is typically serving as an origin server that a CDN such as Amazon CloudFront can pull from\.

For information on the differences between HLS and MediaPackage outputs, see [Choosing between HLS and MediaPackage Output Groups](downstream-system-hls.md#hls-vs-emp)\.

**To set up AWS Elemental MediaPackage**

1. Make sure that the AWS Elemental MediaPackage channel and the AWS Elemental MediaLive channel are in the same AWS Region\. 

1. In AWS Elemental MediaPackage create one channel\. See [Creating a Channel](https://docs.aws.amazon.com/mediapackage/latest/ug/channels-create.html) in the *AWS Elemental MediaPackage User Guide*\. 

1. View the details of the MediaPackage channel\. See [Viewing Channel Details](https://docs.aws.amazon.com/mediapackage/latest/ug/channels-view.html) in the *AWS Elemental MediaPackage User Guide*\. Make a note of the channel ID\. The channel ID is case sensitive\. 
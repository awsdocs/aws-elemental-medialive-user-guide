# HLS output group to MediaPackage<a name="origin-server-hls-emp"></a>

Follow this procedure if you [determined](identify-downstream-system.md) that you will create an HLS output group, and will send to AWS Elemental MediaPackage over HTTPS\.

You and the operator of the downstream system must agree about the destination for the output of the HLS output group\. You will need this information when you [create the MediaLive channel](creating-hls-output-group.md)\.

Note that you can send to AWS Elemental MediaPackage by creating a MediaPackage output group, or by creating an HLS output group\. See [Choosing between the HLS output group and MediaPackage output group](hls-choosing-hls-vs-emp.md) for a description of the differences\. This section describes the second option\. 

Follow this guidance for each HLS output group\.

**To arrange setup of the destination**

1. Ask the MediaPackage user to create one channel on MediaPackage\. Even if the MediaLive channel is a [standard channel](plan-redundancy.md) \(with two pipelines\), you need only one MediaPackage channel\.

1. Arrange with the MediaPackage user to set up HTTPS user credentials\. You must send to MediaPackage over a secure connection\.

1. Obtain the following information:
   + The two URLs \(input endpoints is the MediaPackage terminology\) for the channel\. The two URLs for a channel look like this:

      `https://6d2c.mediapackage.uswest-2.amazonaws.com/in/v2/9dj8/9dj8/channel` 

      `https://6d2c.mediapackage.uswest-2.amazonaws.com/in/v2/9dj8/e333/channel`

     The two URLs are always identical except for the folder just before `channel`\.

     Make sure that you obtain the URLs, not the channel name\.
   + The user name and password to access the downstream system, if the downstream system requires authenticated requests\. Note that these user credentials relate to user authentication, not to the protocol\. User authentication is about whether the downstream system will accept your request\. The protocol is about whether the request is sent over a secure connection\.
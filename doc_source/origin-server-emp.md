# MediaPackage output group<a name="origin-server-emp"></a>

Follow this procedure if you [determined](identify-downstream-system.md) that you will create a MediaPackage output group\. 

You and the operator of the downstream system must agree about the destination for the output of the MediaPackage output group\. You will need this information when you [create the MediaLive channel](creating-mediapackage-output-group.md)\.

Note that you can send to AWS Elemental MediaPackage by creating a MediaPackage output group, or by creating an HLS output group\. See [Choosing between the HLS output group and MediaPackage output group](hls-choosing-hls-vs-emp.md) for a description of the differences\. This section describes the first option\. 

Follow this guidance for each MediaPackage output group\.

**To arrange setup of the destination**

1. Ask the MediaPackage user to create one channel\. Even if the MediaLive channel is a [standard channel](plan-redundancy.md) \(with two pipelines\), you need only one MediaPackage channel\.

1. Obtain the ID of the MediaPackage channel\. The channel ID is case sensitive\. 

Note that you don't need user credentials to send a MediaPackage output to MediaPackage\. MediaLive has permission to write to MediaPackage via the trusted entity\. Someone in your organization should have already set up these permissions\. For more information, see [Reference: summary of requirements for the MediaLive trusted entity](trusted-entity-requirements.md)\.
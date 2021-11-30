# Setting up an RTP push source<a name="rtp-push-upstream"></a>

This section describes how to set up an upstream system that uses the RTP Push protocol to deliver source content from an upstream system that is in your VPC from Amazon VPC\. It describes how to set up the source content on the upstream system, and how to create an input that connects the upstream system to MediaLive\. 

With an RTP push source, the upstream system *pushes* the content to MediaLive\. 

This diagram illustrates the final result of this setup\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/rtp-push-uss-input.png)

To perform this setup, you must work with an operator at the upstream system\.

**Topics**
+ [Obtain information](#setup-rtp-push-obtain-info)
+ [Create an input security group](#setup-isg-rtp-push)
+ [Create an RTP Input](#setup-input-rtp-push)
+ [Ensure correct setup on the upstream system](#setup-uss-rtp-push)
+ [Result of this procedure](#setup-result-rtp-push)

## Obtain information<a name="setup-rtp-push-obtain-info"></a>

Obtain the following information from your contact person at the upstream system:
+ The public network IP addresses\. You need two sets of IP addresses because an RTP input is always a [standard\-class input](class-channel-input.md), even if your channel is a single\-pipeline channel\. For information about input classes, see [Channel class and input class](class-channel-input.md)\.

  These are the sets of IP addresses where the source or sources for the content will appear on the public network\. You need this information to create the input security group\.

  For example:
  + For one source: `203.0.113.19, 203.0.113.58, 203.0.113.25`
  + For the other source: `198.51.100.19, 198.51.100.59, 198.51.100.21`

## Create an input security group<a name="setup-isg-rtp-push"></a>

You must create an input security group\. The security group must allow the *public network IP addresses* to push to MediaLive\. Following from the earlier example, it must allow these addresses:

203\.0\.113\.19, 203\.0\.113\.58, 203\.0\.113\.25, 198\.51\.100\.19, 198\.51\.100\.59, 198\.51\.100\.21

For details about creating an input security group, see [Creating an input security group](create-input-security-groups.md)\.

## Create an RTP Input<a name="setup-input-rtp-push"></a>

After you create the input security group, you must create an input to connect AWS Elemental MediaLive to the content source on the upstream system\. 

For details on creating an RTP push input, see [Creating an RTP push input](input-create-rtp-push.md)\.

## Ensure correct setup on the upstream system<a name="setup-uss-rtp-push"></a>

You must make sure that the upstream system pushes content to the correct locations in MediaLive\.

**To set up for a standard channel**

Follow this procedure if the MediaLive channel is a [standard channel](plan-redundancy.md)\.

1. Provide the operator with this information:
   + The two endpoints \(URLs\) that MediaLive generated when you created the RTP input\. These endpoints are the addresses in the blue boxes in [the diagram after this procedure](#setup-result-rtp-push)\. The URLs include port 5000\. For example: 

     `198.51.100.99:5000`

     `192.0.2.18:5000`

1. Make sure that the operator sets up properly for a standard channel\. They must:
   + Deliver two sources that are identical in terms of video resolution and bitrate\.
   + Make sure that the sources appear on the agreed IP addresses on the public network\. For example:
     + For one source: `203.0.113.19, 203.0.113.58, 203.0.113.25`
     + For the other source: `198.51.100.19, 198.51.100.59, 198.51.100.21`

     You used these addresses when you created the input security group\. If the upstream system doesn't use these addresses, MediaLive will refuse the push\.
   + Push to the correct URLs on MediaLive\. For example, they must push to:

     `198.51.100.99:5000`

     `192.0.2.18:5000`
   + Send over RTP, not UDP\. The UDP protocol is not supported for an input into MediaLive\.

**To set up for a single\-pipeline channel**

Follow this procedure if the MediaLive channel is a [single\-pipeline channel](plan-redundancy.md)\.

1. Provide the operator with this information:
   + Only the first of the two endpoints \(URLs\) that MediaLive generated when you created the RTP input\. This endpoint is one of the addresses in the blue boxes in [the diagram after this procedure](#setup-result-rtp-push)\. The URL includes port 5000\. For example: 

     `198.51.100.99:5000`

1. Make sure that the operator sets up properly for a single\-pipeline channel\. They must:
   + Make sure that the source appears on the agreed IP addresses on the public network\. For example:

     `203.0.113.19, 203.0.113.58, 203.0.113.25`

     You used these addresses when you created the input security group\. If the upstream system doesn't use these addresses, MediaLive will refuse the push\.
   + Push to the correct URL on MediaLive\. For example, they must push to:

     `198.51.100.99:5000`
   + Send over RTP, not UDP\. The UDP protocol is not supported for an input into MediaLive\.

## Result of this procedure<a name="setup-result-rtp-push"></a>

As a result of this setup, an RTP input exists that specifies one or two *endpoint* URLs\. These endpoints are on MediaLive\. 

The upstream system has been set up to push the source content to the two endpoints \(for a standard channel\) or to the first endpoint \(for a single\-pipeline channel\)\. An input security group has been associated with the input\. This input security group has a CIDR block that covers the two URLs that the upstream system pushes, which ensures that MediaLive accepts the pushed content\.

At runtime of the channel, MediaLive reacts to the content that is being pushed and ingests it\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/rtp-push-uss-input.png)
# Setting up an RTMP push source<a name="rtmp-push-upstream"></a>

This section describes how to set up an upstream system that uses the RTMP Push protocol to deliver source content from the public internet\. It describes how to set up the source content on the upstream system, how to create an input security group, and how to create an input that connects the upstream system to MediaLive\. 

With an RTMP Push input, the upstream system *pushes* the content to MediaLive\. 

This diagram illustrates the final result of this setup\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\rtmp-push-uss-input.png)

To perform this setup, you must work with an operator at the upstream system\.

**Topics**
+ [Obtain information](#setup-rtmp-push-obtain-info)
+ [Create an input security group](#setup-isg-rtmp)
+ [Create an RTMP push input](#setup-input-rtmp-push)
+ [Ensure correct setup on the upstream system](#setup-uss-rtmp-push)
+ [Result of this procedure](#setup-result-rtmp-push)

## Obtain information<a name="setup-rtmp-push-obtain-info"></a>

Obtain the following information from your contact person at the upstream system:
+ The application name and application instance for the source content\. \(The application instance is also known as the *stream* or *stream key*\.\) There are two sources for a standard\-class input, or one source for a single\-class input\. For information about input classes and their uses, see [Channel class and input class](class-channel-input.md)\. For information about input classes and their uses, see [Channel class and input class](class-channel-input.md)\. 

  The operator of the upstream system might already have rules for assigning these names\. If not, you might have names that you would like to use\. Make sure that you and the operator of the upstream system are clear about these names\.

  In this example, the application name and instance name are identical\. But they could be different:

  Application name: `live`, and instance name `curling`

  Application name: `live`, and instance name `curling`
+ The public network IP addresses\. These are the sets of IP addresses where the source or sources for the content will appear on the public network\. You need this information to create the input security group\. 

  For example:
  + For one source: `203.0.113.19, 203.0.113.58, 203.0.113.25`
  + For the other source: `198.51.100.19, 198.51.100.59, 198.51.100.21`

  These addresses are the addresses shown in the red boxes in [the diagram after this procedure](#setup-result-rtmp-push)\.

## Create an input security group<a name="setup-isg-rtmp"></a>

You must create an input security group\. The security group must allow the *public network IP addresses* to push to MediaLive\. Following from the earlier example, it must allow these addresses:

203\.0\.113\.19, 203\.0\.113\.58, 203\.0\.113\.25, 198\.51\.100\.19, 198\.51\.100\.59, 198\.51\.100\.21

For details about creating an input security group, see [Creating an input security group](create-input-security-groups.md)\.

## Create an RTMP push input<a name="setup-input-rtmp-push"></a>

After you create the input security group, you must create an input to connect AWS Elemental MediaLive to the content source on the upstream system\. 

For details on creating an RTMP push input, see [Creating an RTMP push input](input-create-rtmp-push.md)\.

## Ensure correct setup on the upstream system<a name="setup-uss-rtmp-push"></a>

You must make sure that the upstream system pushes content to the correct locations in MediaLive\.

**To set up for a standard channel**

Follow this procedure if the MediaLive channel is a [standard channel](plan-redundancy.md)\.

1. Provide the operator with this information:
   + The two endpoints \(URLs\) that MediaLive generated when you created the RTMP input\. These endpoints are the addresses in the blue boxes in [the diagram after this procedure](#setup-result-rtmp-push)\. The URLs include port 1935\. For example: 

     `198.51.100.99:1935/live/curling`

     `192.0.2.18:1935/live/curling`

1. Make sure that the operator sets up properly for a single\-pipeline channel or a standard channel\. 

   If your channel is a single\-pipeline channel, the operator delivers only one source, even though the input is a standard \(dual\-pipeline\) input\. The operator must do the following:
   + Deliver one source\.
   + Make sure that the sources appear on the agreed IP addresses on the public network\. For example:
     + The sources could appear on these addresses: `203.0.113.19, 203.0.113.58, 203.0.113.25`
     + The operator can ignore the other addresses: `198.51.100.19, 198.51.100.59, 198.51.100.21`

     You used these addresses when you created the input security group\. If the upstream system doesn't use these addresses, MediaLive will refuse the push\.
   + Push to one URL on MediaLive, and use the agreed application name and instance name\. For example:

     Push to this URL: `198.51.100.99:1935/live/curling`

     Ignore the other URL: `192.0.2.18:1935/live/curling`

   If your channel is a standard channel, the operator must do the following:
   + Deliver two sources that are identical in terms of video resolution and bitrate\.
   + Make sure that the sources appear on the agreed IP addresses on the public network\. For example:
     + For one source: `203.0.113.19, 203.0.113.58, 203.0.113.25`
     + For the other source: `198.51.100.19, 198.51.100.59, 198.51.100.21`

     You used these addresses when you created the input security group\. If the upstream system doesn't use these addresses, MediaLive will refuse the push\.
   + Push to the correct URLs on MediaLive, and use the agreed application name and instance name\. For example, they must push to:

     `198.51.100.99:1935/live/curling`

     `192.0.2.18:1935/live/curling`

## Result of this procedure<a name="setup-result-rtmp-push"></a>

As a result of this setup, an RTMP push input exists that specifies one or two *endpoint* URLs\. These endpoints are on MediaLive\. 

The upstream system has been set up to push the source content to the two endpoints \(for a standard channel\) or to the first endpoint \(for a single\-pipeline channel\)\. An input security group has been associated with the input\. This input security group has a CIDR block that covers the IP addresses where the pushed source will appear on the public network, which ensures that MediaLive accepts the pushed content\.

At runtime of the channel, MediaLive reacts to the content that is being pushed and ingests it\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images\rtmp-push-uss-input.png)
# Creating an input<a name="create-input"></a>

To provide information about the source of the video asset, you must create an AWS Elemental MediaLive input\. 

**Topics**
+ [Getting ready](#input-create-getready)
+ [Creating a CDI push input in Amazon VPC](input-create-cdi-push.md)
+ [Creating a partner CDI push input in Amazon VPC](input-create-cdi-partners.md)
+ [Creating an Elemental Link input](input-create-link-device.md)
+ [Creating an HLS pull input](input-create-hls-pull.md)
+ [Creating a MediaConnect push input](input-create-push-mediaconnect.md)
+ [Creating an MP4 pull input](mp4-pull-input.md)
+ [Creating a Transport Stream \(TS\) file input](ts-file-input.md)
+ [Creating an RTMP pull input](input-create-rtmp-pull.md)
+ [Creating an RTMP push input](input-create-rtmp-push.md)
+ [Creating an RTMP push input in Amazon VPC](rtmp-push-vpc-input.md)
+ [Creating an RTP push input](input-create-rtp-push.md)
+ [Creating an RTP push input in Amazon VPC](rtp-push-vpc-input.md)

## Getting ready<a name="input-create-getready"></a>

Before you create any input, you should plan the workflow\. Read the following sections:
+ [Preparing the upstream and downstream systems in the MediaLive workflow](container-planning-workflow.md) – You must set up for delivery from the upstream system\. The task of creating an input is part of that delivery setup\. Before you can create the input, you must coordinate with your upstream system and content provider\.
+ [Implementing pipeline redundancy](plan-redundancy-mode.md) – You must decide if you want to implement pipeline redundancy—whether you set up a standard channel or a single\-pipeline channel\. Implementing pipeline redundancy provides resiliency in the channel processing pipeline\.
+ [Implementing automatic input failover](automatic-input-failover.md) – You must decide if you want to implement automatic input failover\. Implementing automatic input failover provides resiliency upstream of the channel, for one of the channel's inputs\.
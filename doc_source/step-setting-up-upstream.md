# Step 6: Coordinate with upstream system and create inputs<a name="step-setting-up-upstream"></a>

After you have identified the upstream system and content source for the channel, you must perform these steps:
+ You must arrange for the operator at the upstream system to perform some setup\.
+ You must create inputs in MediaLive\. 

These two steps create a connection between an address on the upstream system and an address on AWS Elemental MediaLive\. The source content moves from the specified address on the upstream system to the specified address on MediaLive as either a *push* by the upstream system or a *pull* by MediaLive\. 

The connection information is contained in the input that you create\.

The setup is different for each combination of upstream system \(format and delivery protocol\) and input type\. You identified the upstream system and input type when you [assessed the upstream system](evaluate-upstream-system.md)\.

**Result of this step**  
At the end of this step, you will have completed all the steps to prepare the upstream system to deliver content to MediaLive\. 

**Topics**
+ [Setting up a CDI source](cdi-push-vpc-upstream.md)
+ [Setting up an AWS Elemental Link source](device-push-upstream.md)
+ [Setting up an HLS source](hls-upstream.md)
+ [Setting up for a MediaConnect source](emx-upstream.md)
+ [Setting up an MP4 source](mp4-upstream.md)
+ [Setting up an RTMP pull source](rtmp-pull-upstream.md)
+ [Setting up an RTMP push source](rtmp-push-upstream.md)
+ [Setting up an RTMP VPC source](rtmp-vpc-upstream.md)
+ [Setting up an RTP push source](rtp-push-upstream.md)
+ [Setting up an RTP VPC source](rtp-vpc-upstream.md)
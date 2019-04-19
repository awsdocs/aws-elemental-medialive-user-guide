# MediaConnect Push<a name="planning-mediaconnect-push"></a>

MediaLive can accept a flow from AWS Elemental MediaConnect as an input: 
+ The AWS Elemental MediaConnect flow and the MediaLive input must be in the same AWS Region\. If possible, set up AWS Elemental MediaConnect and MediaLive in the same Region\. If that is not possible, then set up a distribution in AWS Elemental MediaConnect to move the source to the same Region as the MediaLive input\. 
+ In AWS Elemental MediaConnect, make sure that the streams in the two flows are identical in terms of resolution and bitrate\. 
+ Keep in mind that AWS Elemental MediaConnect must be pushing its two flows to the MediaLive input before you start the channel\. All push inputs are live inputs, and a live input must be already pushing even if it is not the first input in the channel\. 

For detailed information about setting up AWS Elemental MediaConnect and MediaLive, see [Creating a MediaConnect Push Input](input-push-mediaconnect.md)\.
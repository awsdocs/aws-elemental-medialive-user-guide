# Assessing the Video Source<a name="planning-upstream"></a>

The upstream system is the system that streams the video to AWS Elemental MediaLive\. Examples of an upstream system are a streaming camera or appliance that is directly connected to the internet, or a contribution encoder that is located in a stadium at a sports event\. The upstream system can be on the public internet or in a VPC that you created in Amazon Virtual Private Cloud \(Amazon VPC\)\.

Assess the video source to ensure that it delivers what you expect:
+ Make sure that the upstream system is capable of streaming to your MediaLive input using one of the supported protocols\. See [Supported Input Types and Upstream Systems](inputs-supported-containers.md)\.
+ Determine if your chosen protocol uses a "push" or a "pull\." With a push protocol, the upstream system pushes to MediaLive\. With a pull protocol, MediaLive pulls from the upstream system\. See [Supported Input Types and Upstream Systems](inputs-supported-containers.md)\.
+ Find out how the input—the video codecs, audio codecs, and captions formats—is encoded:
  + Make sure that MediaLive supports the input video codecs and the input audio codecs\. See [Supported Input Types and Upstream Systems](inputs-supported-containers.md)\. 
  + Make sure that MediaLive supports the input captions formats\. Additionally, make sure that MediaLive supports conversion of that input captions format to the output captions format that you want in your specific output types\. See [Reference: Supported Captions](supported-captions.md)\.
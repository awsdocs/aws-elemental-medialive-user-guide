# Step 1: Set up the upstream system<a name="getting-started-step1"></a>

The upstream system is the system that streams the video to MediaLive\. The upstream system can be anything from an on\-premises appliance that is serving as a "contribution encoder" to an application running on a smart phone\. You must perform some setup of your upstream system before you start working with MediaLive\. 

For the purposes of this tutorial, the upstream system must be capable of sending a video stream via RTP push\. 

In a "push" delivery, the upstream system is pushing the stream *from *two IP addresses on the upstream system \(for example, from **203\.0\.113\.111** and from **203\.0\.113\.112**\)\. The upstream system will push *to* two IP addresses on MediaLive \(for example, **rtp://198\.51\.100\.10:5000** and **rtp://192\.0\.2\.131:5000**\)\. In the following steps, you will set up MediaLive so that the two *from* IP addresses are white listed\. Furthermore, MediaLive will generate the two *to* IP addresses\. You will set up the upstream system to push to those addresses\.

**To set up the upstream system**

1. Set up your upstream system to perform an RTP push from two different IP addresses\. You must push from two addresses because MediaLive always expects redundant inputs\.

1. Make a note of the IP addresses\. For example, **203\.0\.113\.111** and from **203\.0\.113\.112**\. You will need these addresses when you set up the input security group in a later step\. 
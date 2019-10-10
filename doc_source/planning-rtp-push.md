# RTP Push<a name="planning-rtp-push"></a>
+ Make sure that the source is a streaming source, not a file source\. A push input works only with a streaming source\.
+ Make sure that the upstream system is set up to send over RTP, not UDP\. The UDP protocol is not supported as an input into MediaLive\.
+ MediaLive works with redundant sources, so the upstream system provide two video streams\. For optimized redundancy, MediaLive runs each source on different encoder pipelines in different Availability Zones\. You don't have to set up these Availability Zones because MediaLive does it for you\.
+ Make sure that the two streams are identical in terms of resolution and bitrate\. 
+ Keep in mind that the upstream system must be pushing the video source to the input before you start the channel\. All push inputs are live inputs, and a live input must be already pushing even if it is not the first input in the channel\. 
+ This information applies if the upstream system is on the public internet\. From the upstream system, obtain the IP addresses that the two streams will push from and make a note of them\. You will need this information to set up the required input security groups for the MediaLive inputs that you will create\.
+ This information applies if the upstream system is in a VPC that you created in Amazon VPC, and you plan to follow the typical plan of creating a VPC input in MediaLive\. From the upstream system, obtain the IP addresses of the two streams that the upstream system will push, and make a note of them\. You will need this information when you identify the VPC security groups for the MediaLive inputs that you will create\.
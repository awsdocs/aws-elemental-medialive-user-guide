# RTMP Push<a name="planning-rtmp-push"></a>
+ Make sure that the source is a streaming source, not a file source\. A push input works only with a streaming source\.
+ MediaLive works with redundant sources, so you provide two video streams\. For optimized redundancy, MediaLive runs each source on different encoder pipelines in different Availability Zones\. You don't have to set up these Availability Zones because MediaLive does it for you\.
+ Make sure that the two streams are identical in terms of resolution and bitrate\. 
+ Determine the application name and application instance for this video source\. 

  The upstream system might have already assigned these names\. These names might be provided to you separately \(for example, the application name is `livestream` and the application instance is `curling`\) or as a path \(`livestream/curling`\)\. Make a note of these names\.

  If the upstream system has not assigned names, you could request names that work for you\. We recommend that you use `live` as the application name and a name of your choosing as the application instance\. Make sure that you and the operator of the upstream system agree on these names\. 
+ Keep in mind that the upstream system must be pushing the video source to the input before you start the channel\. All push inputs are live inputs, and a live input must be already pushing even if it is not the first input in the channel\. 
+ From the upstream system, obtain the IP addresses that the two streams will push from and make a note of them\. You will need this information to set up the required input security groups for the MediaLive inputs that you will create\.
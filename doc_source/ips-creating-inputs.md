# Creating Inputs for Input Switching<a name="ips-creating-inputs"></a>

This section is a supplement to the information in [Working with Inputs in AWS Elemental MediaLive](creating-input.md)\. It provides information specific to inputs that will be used in a channel that contains multiple inputs\. 

When you work with the schedule to set up the switching of inputs, all the inputs must already exist in the channel\. You can't use the schedule to add inputs to a channel after the channel has started\. You can modify the channel itself to add more inputs, but you must stop the channel to do so\.

Therefore, when you set up your workflow you need to do the following:
+ Create all the inputs that you will need through the lifetime of the channel, or at least until the next planned maintenance period\.
+ When you create the channel, add all these inputs to the channel as input attachments\. 

## Rules for Setup<a name="ips-inputs-setup-rules"></a>

To create a live input, create an input of one of these types:
+ MediaConnect Push
+ RTMP Push or Pull
+ RTP Push
+ HLS Pull of a live HLS input

  MediaLive considers an HLS input to be a *live* stream if the **Buffer segments** field has a value from 3 to 10, inclusive\. 

  It considers the input to be a *VOD* asset if that field has a value of 11 or more, or 0, or undefined\. 

  \(To display this field, in **General input settings** for **Network input settings**, choose **Network input**\. For **HLS input settings**, choose **Hls input**\. The **Buffer segments** field appears\.\)

To create a file input, create the type of input:
+ MP4 Pull

For each file input, make sure that you have correctly set up the **Source end behavior** field\. For more information, see [Handling the Transition When the Next Input is Fixed](ips-planning.md#ips-transition-gap)\.

**Note**  
MediaLive does not support the use of HLS VOD assets as inputs in a channel that has multiple input attachments\.
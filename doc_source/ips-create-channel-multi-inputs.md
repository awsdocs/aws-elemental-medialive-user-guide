# Creating a Channel with Multiple Inputs<a name="ips-create-channel-multi-inputs"></a>

This section is a supplement to the information in [Creating a Channel from Scratch](creating-channel-scratch.md)\. It provides information that applies specifically to creating a channel that contains multiple input attachments\. 

Follow the steps for creating a channel, as described in [Creating a Channel from Scratch](creating-channel-scratch.md)\.

Note the following:
+ In the [**Input specifications** section](input-specification.md) for the channel, set up each option to meet or exceed the most demanding of your inputs\.
+ In the [**Input attachments** section](creating-a-channel-step2.md) for the channel, to attach multiple inputs to the channel, for **Input attachments**, choose **Add** once for each input, for up to 20 inputs\. 
  + From 0 to 2 of those input attachments can be live inputs\. One input can be a pull and one a push, or both can be the same\.
  + The remainder, up to the maximum, can be file inputs\. File inputs are always Pull inputs\. 
+ Do not include HLS VOD inputs in the channel\. MediaLive considers an HLS input to be a VOD input if the **Buffer segments** field is set to 11 or higher, or 0, or undefined\. \(To display this field, in **General input settings** for **Network input settings**, choose **Network input**\. For **HLS input settings**, choose **Hls input**\. The **Buffer segments** fields appears\.\)
+ The order in which you create the input attachments is not relevant\. The order in which the input attachments appear in the **Channel** page on the console is not relevant\. The schedule controls the order that the channel will follow to ingest inputs\.
+ In the **General input settings** section for each **Input attachment**, set **Source end behavior** to work correctly\. For information, see [Handling the Transition When the Next Input is Fixed](ips-planning.md#ips-transition-gap)\.
+ In the **General input settings** section for each **Input attachment**, set up the **Video selector**, **Audio selectors**, and **Caption selectors** according to the plan that you created when you assessed the sources\. 

  The setup for video and audio is nearly the same as when the channel has only one input; the only difference is that you set up the video and audio in every input attachment\. 

  The setup for captions is more complicated\. For more information, see [Captions in Channels with Multiple Inputs](captions-channels-multi-input.md) \.
+ In each **Output group**, set up the video, audio, and captions according to the plan that you created when you designed the channel, as described in [Planning the Channel](planning-the-channel.md)\. 
+ Set up other features of MediaLive as needed\. 
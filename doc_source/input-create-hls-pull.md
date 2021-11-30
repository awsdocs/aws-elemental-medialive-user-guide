# Creating an HLS pull input<a name="input-create-hls-pull"></a>

Create your input before you create the channel that ingests the input\. 

You can set up an HLS source as a single\-class or a standard\-class input\. You should have already read [Implementing pipeline redundancy](plan-redundancy-mode.md), to decide the class of channel and class of input you want\.

**To create an HLS pull input**

1. You should have already arranged with the video content provider to [set up the upstream system](hls-upstream.md#setup-hls-obtain-info) for your content\. Make sure that the operator of the upstream system gives you the following information:
   + The full URLs of the locations where MediaLive will pull the M3U8 manifest from\. For example:

     `https://203.0.113.13/sports/curling.m3u8` and 

     `https://198.51.100.54/sports/curling.m3u8`
   + The user name and password \(credentials\) to access the upstream server and/or the license server\. Keep in mind that if you need credentials for both servers, the credentials must be identical\. 

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. Complete the **Input details** section:
   + **Input** name – enter a name\.
   + **Input type** – choose **HLS**\. 

1. In the **Input class** section, choose the class for this input:
   + STANDARD\_INPUT
   + SINGLE\_INPUT

1. In the **Input sources** section, enter the URLs you previously obtained: 
   + If the input is a standard\-class input, complete both fields, to provide two URLs\.
   + If the input is a single\-class input, complete the first field with the URL that you obtained and leave the second field empty\.

1. If the upstream system and/or the license server \(if the HLS source is encrypted\) requires that you provide user credentials, you must also enter the user name and password key for accessing the location\. These credentials are stored on the Systems Manager Parameter Store\. For more information, see [About the feature for creating password parameters](requirements-for-EC2.md#about-EC2Password)\.

   If one of the servers \(upstream system or license server\) requires credentials and the other doesn't, MediaLive presents them to both\. But the server that doesn't need them simply ignores them\.

1. In the **Tags **section, create tags if you want to associate tags with this input\. For more information, see [Tagging AWS Elemental MediaLive resources](tagging.md)\.

1. Choose **Create**\.

   MediaLive creates the input and adds it to the list of inputs\. The input specifies either one or two sources\. The sources don't appear in the list, but if you choose the **Name** link, the details page shows them\. 

   When you start the channel, MediaLive will connect to the upstream system at this source location or locations and pull the HLS manifests into MediaLive:
   + For a channel set up as a standard channel, MediaLive expects the upstream system to provide two sources and will therefore attempt to pull from both source locations\.
   + For a channel set up as a single\-pipeline channel, MediaLive expects the upstream system to provide one source and will therefore attempt to pull from one source location\. 
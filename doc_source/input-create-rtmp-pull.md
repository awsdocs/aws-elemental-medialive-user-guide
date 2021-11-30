# Creating an RTMP pull input<a name="input-create-rtmp-pull"></a>

Create your input before you create the channel that ingests the input\. 

For information about the types of RTMP inputs that MediaLive supports, see [Reference: Supported input containers and codecs](inputs-supported-containers.md)\. 

You can set up an RTMP pull source as a single\-class or a standard\-class input\. You should have already read [Implementing pipeline redundancy](plan-redundancy-mode.md), to decide the class of channel and class of input that you want\.

**To create an RTMP pull input**

1. You should have already arranged with the video content provider to [set up the upstream system](rtmp-pull-upstream.md) for your content\. Make sure that the operator of the upstream system gives you the following information: 
   + The public IP addresses that MediaLive will pull the source content from\. These addresses must include port 1935\. For example:

     `rtmp://203.0.113.13:1935`

     `rtmp://198.51.100.54:1935`
   + The application name and application instance for the source content\. \(The application instance is also known as the *stream* or *stream key*\.\) You need this information to create the RTMP input\. For example:

     Application name: `live`, and instance name `curling`

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. Complete the **Input details** section:
   + **Input** name – enter a name\.
   + **Input type** – choose **RTMP \(pull\)**\. 

1. In the **Input class** section, choose the class for this input:
   + STANDARD\_INPUT
   + SINGLE\_INPUT

1. In the **Input sources** section, enter the URLs you previously obtained: 
   + If the input is a standard\-class input, complete both fields, to provide two URLs\.
   + If the input is a single\-class input, complete the first field with the URL that you obtained and leave the second field empty\.

   For example:

   `rtmp://203.0.113.13:1935/live/curling`

   If the upstream system requires that you provide user credentials, you must also enter the user name and password key for accessing the location\. These credentials are stored on the Systems Manager Parameter Store\. For more information, see [About the feature for creating password parameters](requirements-for-EC2.md#about-EC2Password)\.

1. In the **Tags **section, create tags if you want to associate tags with this input\. For more information, see [Tagging AWS Elemental MediaLive resources](tagging.md)\.

1. Choose **Create**\.

   MediaLive creates the input and adds it to the list of inputs\. The input specifies either one or two sources\. The sources don't appear in the list, but if you choose the **Name** link, the details page shows them\.

   When you start the channel, MediaLive will connect to the upstream system at this source location or locations and pull the content: 
   + If you will set up the channel as a standard channel, MediaLive expects the upstream system to provide two sources and will therefore attempt to pull from both source locations\.
   + If you will set up the channel as a single\-pipeline channel, MediaLive expects the upstream system to provide one source and will therefore attempt to pull from one source location\. 
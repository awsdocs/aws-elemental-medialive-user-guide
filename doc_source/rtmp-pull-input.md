# Creating an RTMP Pull Input<a name="rtmp-pull-input"></a>

Create your input before you create the channel that ingests the input\. 

**To create an RTMP pull input**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. In the **Input details** section, for **Input** name, enter a name\.

1. For **Input type**, choose **RTMP \(pull\)**\. 

1. From the upstream system, obtain the full URLs of the locations where MediaLive will pull the source from\. The upstream system will provide two URLs \(for a channel set up as a [standard channel](plan-redundancy-mode.md)\) or one URL \(for a single\-pipeline channel\)\. For example:

   `rtmp://203.0.113.20:1935/movies/classic`

   `rtmp://203.0.113.88:1935/movies/classic`\.

1. In the **Input sources** section, enter these URLs in one or both fields:
   + If the channel for this input will be set up as a [standard channel](plan-redundancy-mode.md), complete both fields, to provide two URLs\.
   + If the channel for this input will be set up as a single\-pipeline channel, complete the first field with the URL that you obtained and leave the second field empty\.

1. Enter the user name and Amazon EC2 password key for accessing the RTMP location\. These credentials are stored on the Amazon EC2 Systems Manager Parameter Store\. For more information, see [About the Feature for Creating Password Parameters](requirements-for-EC2.md#about-EC2Password)\.

1. In the **Tags **section, create tags if you want to associate tags with this input\. For more information, see [Tagging AWS Elemental MediaLive Resources](tagging.md)\.

1. Choose **Create**\.

   MediaLive creates the input and adds it to the list of inputs\. The input specifies either one or two sources\. The sources don't appear in the list, but if you choose the **Name** link, the details page shows them\.

   When you start the channel, MediaLive will connect to the upstream system at this source location or locations and pull the content: 
   + If the channel for this input will be set up as a standard channel, MediaLive expects the upstream system to provide two sources and will therefore attempt to pull from both source locations\.
   + If the channel for this input will be set up as a single\-pipeline channel, MediaLive expects the upstream system to provide one source and will therefore attempt to pull from one source location\. 
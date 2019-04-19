# Creating an HLS Pull Input<a name="hls-pull-input"></a>

Create your input before you create the channel that ingests the input\. 

The HLS input can be encrypted or unencrypted\. For information on preparing encrypted content to ensure that MediaLive can successfully unencrypt it, see [HLS Pull](planning-hls-pull.md)\.

**To create an HLS pull input**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. In the **Input details** section, for **Input** name, enter a name\.

1. For **Input type**, choose **HLS**\. 

1. From the upstream system, obtain the full URLs of the locations where MediaLive will pull the M3U8 manifest source from\. The upstream system will provide two URLs \(for a [standard channel](plan-redundancy-mode.md)\) or one URL \(for a single\-pipeline channel\)\.

   The URLs will have one of these formats:
   + For a location that supports HTTP or HTTPS, enter an HTTP or HTTPS URL\. For example, `https://203.0.113.13/newschannel/anytownusa.m3u8` and `https://203.0.113.54/newschannel/anytownusa.m3u8`\.
   + For a manifest that is stored on AWS Elemental MediaStore, the URL must include the data endpoint for the container\. For example, the M3U8 file is called `mlaw.m3u8`, and it is stored in the container "movies" in the folder path `premium/canada`\. The URL for the container might be **eri39n\.data\.mediastore\.us\-west\-2\.amazonaws\.com**\. The value that you enter in this field would be **mediastoressl://eri39n\.data\.mediastore\.us\-west\-2\.amazonaws\.com/premium/canada/mlaw\.m3u8**\. 
   + For a manifest that is stored on Amazon S3, enter the protocol as **s3** or **s3ssl**, and then enter the bucket name and object for the manifest\. For example, `s3://movies/mlaw.m3u8` and `s3://movies/redundant/mlaw.m3u8`\. 

1. In the **Input sources** section, enter these URLs in one or both fields: 
   + If the channel for this input will be set up as a [standard channel](plan-redundancy-mode.md), complete both fields, to provide two URLs\.
   + If the channel for this input will be set up as a single\-pipeline channel, complete the first field with the URL that you obtained and leave the second field empty\.

1. If you use a secure connection \(s3ssl\), you must also enter the user name and Amazon EC2 password key for accessing the location\. These credentials are stored on the Amazon EC2 Systems Manager Parameter Store\. For more information, see [About the Feature for Creating Password Parameters](requirements-for-EC2.md#about-EC2Password)\.

1. In the **Tags **section, create tags if you want to associate tags with this input\. For more information, see [Tagging AWS Elemental MediaLive Resources](tagging.md)\.

1. Choose **Create**\.

   MediaLive creates the input and adds it to the list of inputs\. The input specifies either one or two sources\. The sources don't appear in the list, but if you choose the **Name** link, the details page shows them\. 

   When you start the channel, MediaLive will connect to the upstream system at this source location or locations and pull the content:
   + For a channel set up as a standard channel, MediaLive expects the upstream system to provide two sources and will therefore attempt to pull from both source locations\.
   + For a channel set up as a single\-pipeline channel, MediaLive expects the upstream system to provide one source and will therefore attempt to pull from one source location\. 
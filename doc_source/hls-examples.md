# HLS Example<a name="hls-examples"></a>

This example shows how to set up the fields that relate to destinations\. They don't show how to set up other fields such as fields in the individual outputs\.

You want to stream the curling game to MediaPackage\. You want to create three outputs: high, medium, and low bitrate\. 


| Field | Value | 
| --- | --- | 
| CDN settings in HLS settings section | hls webdavThis is the type of connection that MediaPackage uses\. Change the other CDN fields that appear, or keep the defaults\.  | 
| Fields in Location section | Keep the defaults in all the fields; these fields are not used in this example\.  | 
| URL in HLS group destination A section | For example, https://62e3c93793c034c\.mediapackage\.us\-west\-2\.amazonaws\.com/in/v1/9378dje8/channel\.The URLs are the **Input URLs** from the channel in AWS Elemental MediaPackage\. As discussed in [Setting Up the Downstream System](setting-up-downstream-system.md), the input in MediaPackage is identical to the output from AWS Elemental MediaLive\. This input URL must already exist in MediaPackage\.Note that in MediaPackage, URLs always end in "channel", so the base file name in MediaLive must be "channel"\.  | 
| Credentials in HLS group destination A section | MediaPackage accepts only authenticated requests, so you must enter a user name and a password that is known to MediaPackage\. For the password, enter the name of the password stored on the AWS Systems Manager Parameter Store\. Don't enter the password itself\. For more information, see [Access to Amazon EC2 Systems Manager Parameter Store](https://docs.aws.amazon.com/medialive/latest/ug/about-EC2Password.html)\.  | 
| URL in HLS group destination B section | For example, https://60dei849783734c\.mediapackage\.us\-west\-2\.amazonaws\.com/in/v1/6da5ba717b357a/channel\. | 
| Credentials in HLS group destination B section | Enter a user name and password as for the URL for destination A\. The credentials are probably the same for both URLs, but they might not be\. | 
| Name modifier in HLS outputs section |  Choose **Add output** twice: two more **Output** lines are added to this section, for a total of three lines\. In each line, enter a modifier: **\_high**, **\_medium**, and **\_low**\.  | 

As a result, files are created with the following names:
+ One master manifest: `channel.m3u8`
+ One rendition manifest for each output: `channel_high.m3u8`, `channel_medium.m3u8`, `channel_low.m3u8`
+ TS files for each output: 
  + `channel_high.00001.ts`, `channel_high.00002.ts`, `channel_high.00003.ts`, and so on
  + `channel_medium.00001.ts`, `channel_medium.00002.ts`, `channel_medium.00003.ts`, and so on 
  + `channel_low.00001.ts`, `channel_low.00002.ts`,` channel_low.00003.ts`, and so on

The files will be published to both URL inputs on MediaPackage\.
# HLS Example<a name="hls-examples"></a>

This example shows how to set up the fields relating to destinations\. They do not show how to set up other fields such as field in the individual outputs\.

You want to stream the curling game to \. You want toAWS Elemental MediaPackage create three outputs: high, medium, and low bitrate\. 


| Field | Value | 
| --- | --- | 
| CDN settings  in HLS settings section | hls webdavThis is the type of connection that AWS Elemental MediaPackage uses\. Change the other CDN fields that appear, or leave the defaults\.  | 
| Location in HLS settings section | Leave the defaults in all the fields; these fields are not used in this example\.  | 
| Primary URL in HLS destinations section | For example, https://62e3c93793c034c\.mediapackage\.us\-west\-2\.amazonaws\.com/in/v1/9378dje8/channel The URLs are the Input URLS from the channel in AWS Elemental MediaPackage\. As discussed in [[ERROR] BAD/MISSING LINK TEXT](setting-up-downstream-system.md), the input in AWS Elemental MediaPackage is identical to the output from AWS Elemental MediaLive\. This input URL must already exist in AWS Elemental MediaPackage\.Note that in AWS Elemental MediaPackage, URLs always end in "channel", so the base filename in AWS Elemental MediaLive must be "channel"\.  | 
| Credentials in Primary URL in HLS destinations section | The protocol for AWS Elemental MediaPackage is HTTPS, which is a secure connection, so you must type a username and a password that is known to AWS Elemental MediaPackage\. For the password, enter the EC2 Parameter store name value \(not the actual password\)\. For more information, see [Access to Amazon EC2 Systems Manager Parameter Store](https://docs.aws.amazon.com/medialive/latest/ug/about-EC2Password.html)\.  | 
| Backup URL in HLS destinations section | For example, https://60dei849783734c\.mediapackage\.us\-west\-2\.amazonaws\.com/in/v1/6da5ba717b357a/channel | 
| Credentials in Backup URL in HLS destinations section | Type a username and password, as for the primary URL\. The credentials are probably the same as for the primary URL, but they may not be\. | 
| Name modifier in HLS outputs section |  Choose **Add output** twice: two more Output lines are added to this section, for a total of three lines\. In each line, enter a modifier: **\_high**, **\_medium**, and **\_low**\.  | 

Result: Files will be created with the following names:

+ One master manifest: `channel.m3u8`

+ One rendition manifest for each output: `channel_high.m3u8`, `channel_medium.m3u8`, `channel_low.m3u8`

+ TS files for each output: 

  + `channel_high.00001.ts`, `channel_high.00002.ts`, `channel_high.00003.ts`, and so on\. 

  + `channel_medium.00001.ts`, `channel_medium.00002.ts`, `channel_medium.00003.ts`, and so on\. 

  + `channel_low.00001.ts`, `channel_low.00002.ts`,` channel_low.00003.ts`, and so on\.

The files will be published to both URL inputs on AWS Elemental MediaPackage \. 
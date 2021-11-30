# MediaPackage example<a name="hls-example-mediapackage"></a>

This example shows how to set up the destination fields if the downstream system for the HLS ouptput group is MediaPackage\.

Assume that you want to stream the curling game and to create three outputs: high, medium, and low bitrate\. 


| Field | Value | 
| --- | --- | 
| CDN settings in HLS settings section | hls webdav | 
| URL in HLS group destination A section |  https://62e3c93793c034c\.mediapackage\.us\-west\-2\.amazonaws\.com/in/v1/9378dje8/channel\. | 
| Credentials in HLS group destination A section | MediaPackage accepts only authenticated requests, so you must enter a user name and a password that is known to MediaPackage\. For the password, enter the name of the password stored on the AWS Systems Manager Parameter Store\. Don't enter the password itself\. For more information, see [Requirements for AWS Systems Manager—creating password parameters in parameter store ](requirements-for-EC2.md)\.  | 
| URL in HLS group destination B section | https://60dei849783734c\.mediapackage\.us\-west\-2\.amazonaws\.com/in/v1/6da5ba717b357a/channel\. | 
| Credentials in HLS group destination B section | Enter a user name and password for the URL for destination B\. The credentials are probably the same for both URLs, but they might not be\. | 
| Name modifier in HLS outputs section |  Choose **Add output** twice: two more **Output** lines are added to this section, for a total of three lines\. In each line, enter a modifier: **\-high**, **\-medium**, and **\-low**\.  | 
| Directory Structure and Segments Per Subdirectory in Location section | MediaPackage does not use these fields, therefore leave them blank\.  | 

As a result, files are created with the following names:
+ One main manifest: **channel\.m3u8**
+ One child manifest for each output: **channel\-high\.m3u8**, **channel\-medium\.m3u8**, **channel\-low\.m3u8**
+ TS files for each output: 
  + **channel\-high\-00001\.ts**, **channel\-high\-00002\.ts**, **channel\-high\-00003\.ts**, and so on
  + **channel\-medium\-00001\.ts**, **channel\-medium\-00002\.ts**, **channel\-medium\-00003\.ts**, and so on 
  + **channel\-low\-00001\.ts**, **channel\-low\-00002\.ts**,** channel\-low\-00003\.ts**, and so on

The files will be published to both URL inputs on MediaPackage\.
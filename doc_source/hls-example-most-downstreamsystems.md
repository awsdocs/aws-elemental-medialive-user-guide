# Example for an HTTP or HTTPS server<a name="hls-example-most-downstreamsystems"></a>

This example shows how to set up the destination fields if the downstream system is an HTTPS server that uses basic PUT\. 

Assume that you want to stream the curling game and to create three outputs: high, medium, and low bitrate\.


| Field | Value | 
| --- | --- | 
| CDN settings in HLS settings section | Hls basic putChange the other CDN fields according to the instructions from the downstream system\.  | 
| URL in HLS group destination A section | For example:**https://203\.0\.113\.55/sports/curling** | 
| Credentials in HLS group destination A section | If the downstream system requires authenticated requests, enter the user name provided by the downstream system\. For the password, enter the name of the password stored on the AWS Systems Manager Parameter Store\. Don't enter the password itself\. For more information, see [Requirements for AWS Systems Manager—creating password parameters in parameter store ](requirements-for-EC2.md)\.  | 
| URL in HLS group destination B section | For example:**https://203\.0\.113\.82/sports/curling** | 
| Credentials in HLS group destination B section | Enter a user name and password for the URL for destination B, if applicable\. The credentials are probably the same for both URLs, but they might not be\. | 
| Name modifier in HLS outputs section |  Choose **Add output** twice: two more **Output** lines are added to this section, for a total of three lines\. In each line, enter a modifier: **\-high**, **\-medium**, and **\-low**\.  | 
| Directory Structure and Segments Per Subdirectory in Location section |  Assume that the downstream system doesn't use these fields\.  | 

As a result, files are created with the following names:
+ One main manifest: `curling.m3u8`
+ One child manifest for each output: `curling-high.m3u8`, `curling-medium.m3u8`, `curling-low.m3u8`
+ TS files for each output: 
  + `curling-high-00001.ts`, `curling-high-00002.ts`, `curling-high-00003.ts`, and so on
  + `curling-medium-00001.ts`, `curling-medium-00002.ts`, `curling-medium-00003.ts`, and so on 
  + `curling-low-00001.ts`, `curling-low-00002.ts`, ` curling-low-00003.ts`, and so on

The files will be published to two hosts at the downstream system, and in a folder called `sports` on each host\.
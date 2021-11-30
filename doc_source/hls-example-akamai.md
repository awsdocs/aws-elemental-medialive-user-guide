# Akamai example<a name="hls-example-akamai"></a>

This example shows how to set up the destination fields if the downstream system is an Akamai server\. 

Assume that you want to stream the curling game and to create three outputs: high, medium, and low bitrate\. 


| Field | Value | 
| --- | --- | 
| CDN settings in HLS settings section | HLS akamai Select this setting if you are using Akamai Token Authentication\. Change the other CDN fields according to the instructions from Akamai\.HLS basic put Select this setting if you are using digest authentication\. Change the other CDN fields according to the instructions from Akamai\. | 
| URL in HLS group destination A section | For example:**http://p\-ep50002\.i\.akamaientrypoint\.net/50002/curling**Mapping this URL to the Akamai terminology: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/hls-example-akamai.html) | 
| Credentials in HLS group destination A section | If Akamai requires authenticated requests, enter a user name and a password that is known to Akamai\. For the password, enter the name of the password stored on the AWS Systems Manager Parameter Store\. Don't enter the password itself\. For more information, see [Requirements for AWS Systems Manager—creating password parameters in parameter store ](requirements-for-EC2.md)\.  | 
| URL in HLS group destination B section | For example:**http://b\-ep50002\.i\.akamaientrypoint\.net/50002/curling**Mapping this URL to the Akamai terminology: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/hls-example-akamai.html) | 
| Credentials in HLS group destination B section | Enter a user name and password for the URL for the other destination, if applicable\. The credentials are probably the same for both URLs, but they might not be\. | 
| Name modifier in HLS outputs section |  Choose **Add output** twice: two more **Output** lines are added to this section, for a total of three lines\. In each line, enter a modifier: **\-high**, **\-medium**, and **\-low**\.  | 
| Directory Structure and Segments Per Subdirectory in Location section |  Complete the fields according to the instructions from Akamai\.  | 

As a result, files are created with the following names:
+ One main manifest: **curling\.m3u8**
+ One child manifest for each output: **curling\-high\.m3u8**, **curling\-medium\.m3u8**, **curling\-low\.m3u8**
+ TS files for each output: 
  + `curling-high-00001.ts`, `curling-high-00002.ts`, `curling-high-00003.ts`, and so on
  + `curling-medium-00001.ts`, `curling-medium-00002.ts`, `curling-medium-00003.ts`, and so on 
  + `curling-low-00001.ts`, `curling-low-00002.ts`,` curling-low-00003.ts`, and so on

The files will be published to two Akamai hosts – **p\-ep50002\.i\.akamaientrypoint\.net** and **b\-ep50002\.i\.akamaientrypoint\.net** and in a folder called **5002** on each host\.
# Microsoft Smooth Example<a name="smooth-examples"></a>

These examples show how to set up the fields relating to destination\. They do not show how to set up other fields such as field in the individual outputs\.

You want to stream the curling game to an origin server that supports Microsoft Smooth\. You want to create three outputs: high, medium, and low bitrate\. 


| Field | Value | 
| --- | --- | 
| Primary URL in Microsoft Smooth destinations section | For example, https://192\.0\.2\.0/sports/curling/$d$For information on identifiers for variable data \(such as $d$\), see [[ERROR] BAD/MISSING LINK TEXT](variable-data-identifiers.md)\. | 
| Credentials in Primary URL in HLS destinations section | The protocol is HTTPS, which is a secure connection, so you must type a username and a password that is known to the origin server\. For the password, enter the EC2 Parameter store name value \(not the actual password\)\. For more information, see [Access to Amazon EC2 Systems Manager Parameter Store](https://docs.aws.amazon.com/medialive/latest/ug/about-EC2Password.html)\.  | 
| Backup URL in Microsoft Smooth destinations section | For example, https://192\.0\.2\.230/sports/curling/$d$ | 
| Credentials in Backup URL in HLS destinations section | Type a username and password, as for the primary URL\. The credentials are probably the same as for the primary URL, but they may not be\. | 
| Name modifier in Microsoft Smooth outputs section | Leave blank; in this example, a name modifier is not used\. | 

Result: Assuming the channel is run on November 30, 2017, then files will be created with the following names:

+ One master manifest:` 20171130.isml`

+ A set of video, audio and captions for output 1: `20171130_high.ismv`, `20171130_high.isma`, `20171130_high.ismt`

+ A set of video, audio and captions for output 2: `20171130_medium.ismv`, `20171130_medium.isma`, `20171130_medium.ismt`

+ A set of video, audio and captions for output 3: `20171130_low.ismv`, `20171130_low.isma`, `20171130_low.ismt`

The files will be published to both destinations: `https://192.0.2.0/sports/curling/$d$` and `https://192.0.2.230/sports/curling/$d$`\.
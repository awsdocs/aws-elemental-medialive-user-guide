# Microsoft Smooth Example<a name="smooth-examples"></a>

The following examples show how to set up the fields that relate to destination\. They do not show how to set up other fields such as fields in the individual outputs\.

You want to stream the curling game to an origin server that supports Microsoft Smooth\. You want to create three outputs: high, medium, and low bitrate\. 


| Field | Value | 
| --- | --- | 
| URL in the Microsoft Smooth group destination A section | For example, https://203\.0\.113\.18/sports/curling/$d$\.For information about identifiers for variable data \(such as `$d$`\), see [Reference: Identifiers for Variable Data](variable-data-identifiers.md)\. | 
| Credentials in the Microsoft Smooth group destination A section | The Microsoft origin server accepts only authenticated requests, so you must enter a user name and a password that is known to that server\. For the password, enter the name of the password stored on the AWS Systems Manager Parameter Store\. Don't enter the password itself\. For more information, see [Access to Amazon EC2 Systems Manager Parameter Store](https://docs.aws.amazon.com/medialive/latest/ug/about-EC2Password.html)\.  | 
| URL in the Microsoft Smooth group destination B section | For example, https://203\.0\.113\.77/sports/curling/$d$\. | 
| Credentials in the Microsoft Smooth group destination Bsection | Enter a user name and password, as for the URL for destination A\. The credentials are probably the same for both URLs, but they might not be\. | 
| Name modifier in the Microsoft Smooth outputs section | Leave blank; in this example, a name modifier is not used\. | 

Result: If the channel is run on November 30, 2017, files are created with the following names:
+ One master manifest: `20171130.isml`
+ A set of video, audio, and captions for output 1: `20171130_high.ismv`, `20171130_high.isma`, `20171130_high.ismt`
+ A set of video, audio, and captions for output 2: `20171130_medium.ismv`, `20171130_medium.isma`, `20171130_medium.ismt`
+ A set of video, audio, and captions for output 3: `20171130_low.ismv`, `20171130_low.isma`, `20171130_low.ismt`

The files will be published to both destinations: `https://203.0.113.18/sports/curling/$d$` and `https://203.0.113.77/sports/curling/$d$`\.
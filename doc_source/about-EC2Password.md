# Access to Amazon EC2 Systems Manager Parameter Store<a name="about-EC2Password"></a>

The Amazon EC2 Systems Manager Parameter Store is used extensively in AWS Elemental MediaLive\. It is likely that you will use this store\. The store holds passwords that the AWS Elemental MediaLive needs in order to retrieve and store files externally\. 

Some of the features that store passwords in this way are:

+ An input of type RTMP Pull or type HLS Pull\. The connection to the source is always secure\.

+ Fields in the channel that hold the URL to an external file, if the connection is secure\.Examples of this type of field are the Avail blanking image, and a source captions file that is an external file\.

+ The destination in an HLS output group or a Micrsoft Smooth output group, if the connection is secure\.

In all these cases, if the connection is secure \(typically HTTPS\), then AWS Elemental MediaLive needs the username and password \(stored in a parameter\)\.

**How It Works**

The password parameter feature ensures that you are not storing passwords in plain text on the console\. Instead, you create a password parameter in Amazon EC2 Systems Manager Parameter Store\. The parameter is a name/value pair where the name is something like "corporateStorageImagesPassword" and the value is the actual password\. When creating a channel or input in AWS Elemental MediaLive, you specify the password parameter name instead of the password\. Then when AWS Elemental MediaLive needs the password \(in order to either read or write to the external location\), it sends the password parameter name to the Amazon EC2 Systems Manager Parameter Store and gets back the actual password in response\.

Wherever a password field appears on the console, AWS Elemental MediaLive includes a feature that lets you:

+ Specify a password parameter that has already been created in Amazon EC2 Systems Manager Parameter\.

+ Or create a password parameter "on the spot"\. You type in a name and the actual password\. 

**Required Permissions**

For any user to create a password parameter "on the spot", AWS Elemental MediaLive must have a trusted entity role that includes Amazon EC2 Systems Manager Parameter\. See [[ERROR] BAD/MISSING LINK TEXT](trusted-entity-role.md)\.
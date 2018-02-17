# Setting up the Downstream System<a name="setting-up-downstream-system"></a>

 You must set up the device or application that will be downstream of AWS Elemental MediaLive\. The downstream system is different for different outputs\.


| Output Protocol | Typical Downstream Systems | 
| --- |--- |
| Archive |  An AWS S3 bucket\.  | 
| HLS |     A CDN that uses HTTP \(or HTTPS\) PUT\.   A CDN that uses HTTP or HTTPS WebDAV\. AWS Elemental MediaPackage is an example of this kind of CDN\.   An Akamai CDN \(this always uses HTTP or HTTPS\)\.   An AWS Elemental MediaStore container\.   An AWS S3 bucket\.   Both AWS Elemental MediaPackage and AWS Elemental MediaStore can serve as CDNs\. Or they can serve as origin servers that a CDN such as Amazon CloudFront can pull from\.  | 
| Microsoft Smooth | A CDN that uses HTTP \(or HTTPS\) PUT\. Typically, the downstream system is a Microsoft IIS server\. | 
| UDP | An address that can communicate over UDP or RTP\. | 

The output from AWS Elemental MediaLive will be considered input to this downstream system\. You must set up this downstream “input” now because when you are creating the AWS Elemental MediaLive channel you will need the addresses of that input\. 

AWS Elemental MediaLive always works in redundant mode – it always encodes the input to two destinations \(which are inputs from the downstream system's point of view\)\. 

1. In your downstream system, set up two inputs\. 

   + If the downstream system is AWS Elemental MediaPackage, create two AWS Elemental MediaPackage channels\. Make a note of the input addresses, the input username, and input password\. 

   + If the downstream system is an AWS S3 bucket, create two buckets\. Make a note of the full path of the buckets\. 

   + If the downstream system is an AWS Elemental MediaStore container, create two containers\. Make a note of the full path of the container and the data plane value of the container\.

   + If the downstream system is a CDN, set up so that the CDN expects output at both its inputs\. Make a note of the input addresses, and of the input username and input password, if applicable\. 

1. Put in place some mechanism for ensuring that the output from AWS Elemental MediaLive is arriving successfully:

   + If the output is an archive input, some system downstream of AWS Elemental MediaLive must make sure that one or other of the buckets contains the complete file output\.

   + If the output is a stream to AWS S3 or AWS Elemental MediaStore, some system downstream of AWS Elemental MediaLive must make sure that or other of the buckets is continually receiving the streaming output\. The system downstream of AWS S3 or AWS Elemental MediaStore should only access complete content\.

   + If the downstream system is a CDN, make sure it has logic for detecting a loss in input and switching from one input to the other when that loss is detected\.
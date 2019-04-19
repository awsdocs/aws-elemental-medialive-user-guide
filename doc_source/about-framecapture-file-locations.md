# About Frame Capture Locations and File Names<a name="about-framecapture-file-locations"></a>

The location of frame capture output files is constructed from several parts\. Some of these parts are derived from fields in the **Frame capture** output group and the individual outputs, and some are set automatically by MediaLive:
+ The two **URL** fields in the **Frame capture group destinations** section\. The URL consists of a *protocol* portion, a *path* portion, and a *base filename* portion\. 

  For example, assume that the URL is `s3ssl://sports_delivery/highlights/20180820/curling_`\. These are the parts of that URL:

  `s3ssl://` is the protocol\. The protocol is always `s3ssl://`, to indicate that the destination is an Amazon S3 bucket\.

  `sports_delivery/highlights/20180820/` is the path\. The path is required and consists of a bucket and folders, terminated by a slash\.

  `curling_` is the base file name\. Do not terminate the base file name with a slash\.
+ The **Name modifier** field in the **Frame capture outputs** section\. Optional\. This modifier forms part of the output file name\. 
+ A sequential counter, which is automatically set to a 5\-digit number starting with 00001\.
+ An extension, which is always `.jpg`\.

The values from these components are put together to form the location:

**protocol \+ path \+ base\_filename \+ name\_modifier \+ sequential\_counter \+ \.extension**

The protocol and path point to an Amazon S3 bucket\. 

The base filename, name modifier, sequential counter, and extension form the name of each file in the bucket\.

For example, the path for the bucket for the output might be the following:

`s3ssl://sports_delivery/highlights/20180820/`

The first file for an output might be the following:

`curling_low_00001.jpg`
# About Archive Locations and File Names<a name="about-archive-file-locations"></a>

The location of archive output files is controlled by several fields in the **Archive** output group and the individual outputs:
+ The two **URL** fields in the **Archive group destinations** section\. The URL consists of a *protocol* portion, a *path* portion and a *base filename* portion\. 

  For example, assume that the URL is `s3ssl://interviews/3series/Delivery/3633_WangXiuLan`\.

  `s3ssl://` is the protocol\. The protocol is always `s3ssl://`, to indicate that the destination is an Amazon S3 bucket\.
+ `interviews/3series/Delivery/` is the path\. The path is required and consists of a bucket and folders, terminated by a slash\.

  `3633_WangXiuLan` is the base file name\. Do not terminate the base file name with a slash\.
+ The **Name modifier** field in the **Archive outputs** section\. Required\. The string forms part of the file name\.
+ The **Extension** field in the **Archive outputs** section\. The extension for the file name\. Required only if you don't want to use the default \(`.ts`\)\.
+ The **Rollover interval** field in the **Archive settings** section\. Required\. For example, **600** divides the output into separate files, each 600 seconds \(10 minutes\) long\. Each file name includes a six\-digit sequential counter, such as 000000, 000001, and so on\. 

  Each time the rollover expires, MediaLive closes the current file on Amazon S3 and starts a new file\. The current file is visible on Amazon S3 only after it has closed\.

The values from these fields are put together to form the location:

**protocol path base\_filename name\_modifier sequential\_counter extension**

For more information, see the [examples](archive-examples.md)\. 
# Fields for Archive Group<a name="archive-group-fields"></a>

## Archive Settings<a name="archive-settings"></a>

+ Enter a name for the output group\. For example, **Sports Game 10122017 ABR** or **tvchannel59**\.

+ In **Archive settings**, choose **Additional settings** and complete the **Rollover Interval** field , if desired\. This field interacts with the fields in the **Archive destinations** section lower down on this panel\. 

## Archive Destinations<a name="archive-destinations"></a>

You must specify the destinations for this output\. Each destination is a bucket and object in an AWS S3 account\. You must be set up so that AWS Elemental MediaLive can access your AWS S3 account; see [[ERROR] BAD/MISSING LINK TEXT](about-S3-access.md)\. 

You must specify two destinations because AWS Elemental MediaLive works in redundant mode for outputs: it requires two destinations\. The URL is one piece of the information use for the location and filenames of the output file; see [[ERROR] BAD/MISSING LINK TEXT](#about-archive-file-locations) \. 

## Archive Outputs<a name="archive-outputs"></a>

This section contains fields related to the encoding of the video, audio, and captions in the output, and related to the packaging and delivery of the output\. 

+ Choose **Add output** if you want more than one output in this output group\. An **Output** line is added for each output\. Setup of the individual outputs is described in [[ERROR] BAD/MISSING LINK TEXT](creating-a-channel-step5.md)\.

+ In the **Name modifier** field for each output, type a modifier, if appropriate\. See [[ERROR] BAD/MISSING LINK TEXT](#about-archive-file-locations) for uses for this field\.

## About Archive Locations and Filenames<a name="about-archive-file-locations"></a>

The location of archive output files is controlled by several fields in the Archive output group and the individual outputs\.

+ The two **URL** fields in the **Archive destinations** section\. The URL consists of a *protocol* portion, a *path *portion and a *base filename *portion\. 

  For example, assume the URL is `s3ssl://interviews/3series/Delivery/3633_WangXiuLan`\.

  **s3ssl://** is the protocol\. The protocol is always **s3ssl://**, to indicate that the destination is an AWS S3 bucket\.

  `interviews/3series/Delivery/` is the path\. The path is required and consists a bucket and folders, terminated by a slash\.

  `3633_WangXiuLan` is the base filename\. The base filename is optional\. If you omit it, AWS Elemental MediaLive uses the name of the input as the base filename\.

+ The **Name modifier **field in the **Archive outputs **section\. Required\. The string forms part of the filename\.

+ The **Extension** field in the **Archive outputs **section\. The extension for the filename\. Required only if you do not want to use the default \(`.ts`\)\.

+ The **Rollover interval **field in the **Archive settings **section\. Required\. For example, **600** divides the output into separate files, each 600 seconds \(10 minutes\) long\. Each filename includes a 6\-digit sequential counter, 000000, 000001, and so on\.

The values from these fields are put together to form the location:

**protocol path base\_filename name\_modifier sequential\_counter extension**

For more information, see the examples\. 
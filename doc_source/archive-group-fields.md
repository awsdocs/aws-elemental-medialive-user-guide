# Fields for the Archive Group<a name="archive-group-fields"></a>

You must provide information about the destination for each Archive output group\. This destination information applies to all the outputs in the individual Archive output group\.

## Archive Destinations<a name="archive-destinations"></a>

For**Archive group destination A** and **Archive group destination B**, specify two destinations when the channel is set up as a [standard channel](channel-class.md), or one destination when it is set up as a single\-pipeline channel\. The URL is one piece of the information that is used for the location and file names of the output file\. For more information, see [About Archive Locations and File Names](about-archive-file-locations.md)\. 

Each destination is a bucket and object in an Amazon S3 account\. 

## Archive Settings<a name="archive-settings"></a>
+ For **Name**, enter a name for the output group\. For example, **Sports Game 10122017 ABR** or **tvchannel59**\.
+ For **Additional settings**, optionally complete the **Rollover Interval** field\. This value is one piece of the information that is used for the [location and file names](about-archive-file-locations.md) of the media files\. 

## Archive Outputs<a name="archive-outputs"></a>

This section contains fields that relate to the encoding of the video, audio, and captions in the output, and that relate to the packaging and delivery of the output\. 
+ If you want more than one output in this output group, choose **Add output**\. An **Output** line is added for each output\. Setup of the individual outputs is described in [Step 6: Create Outputs](creating-a-channel-step5.md)\.
+ For **Name modifier** for each output, enter a modifier, if appropriate\. For uses for this field, see [About Archive Locations and File Names](about-archive-file-locations.md)\. 
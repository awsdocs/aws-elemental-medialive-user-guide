# Fields for the Frame Capture Group<a name="framecapture-group-fields"></a>

You must provide information about the destination for each Frame Capture output group\. 

## Frame Capture Destinations<a name="framecapture-destinations"></a>

For **Frame Capture group destination A** and **Archive group destination B**, specify two destinations when the channel is set up as a [standard channel](channel-class.md), or one destination when it is set up as a single\-pipeline channel\. The URL is one piece of the information that is used for the location and file names of the output file\. For more information, see [About Frame Capture Locations and File Names](about-framecapture-file-locations.md)\. 

Each destination is a bucket and object in an Amazon S3 account\. 

## Archive Settings<a name="framecapture-settings"></a>

For **Name**, enter a name for the output group\. The name must be unique in this channel\. For example, **Sports Game Frame Capture**\.

## Archive Outputs<a name="framecapture-outputs"></a>

For **Name modifier** for each output, enter a modifier, if appropriate\. For uses for this field, see [About Frame Capture Locations and File Names](about-framecapture-file-locations.md)\.
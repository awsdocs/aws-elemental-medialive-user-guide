# Result of this procedure<a name="mediapackage-create-result"></a>

With a MediaPackage output group, you don't configure as many fields as you do with a regular HLS output group\. Instead, MediaLive automatically sets up the output group as follows:

**Destination**
+ The output from pipeline 0 is mapped to the first ingest endpoint in the MediaPackage channel\. The output from pipeline 1 \(if you have set up a standard channel\) is mapped to the second ingest endpoint\.

  The mapping of each pipeline to an ingest endpoint never changes\. The only change that can occur in the mappings is if you upgrade a single\-pipeline input to a standard\-class input, or upgrade a single\-pipeline channel to a standard channel\. In both these cases, pipeline 1 will be mapped to the second ingest endpoint \(which has always existed\)\.

  You can view details of the mappings after you have created the channel\. Follow the steps in [Viewing channel details](https://docs.aws.amazon.com/mediapackage/latest/ug/channels-view) in the *AWS Elemental MediaPackage User Guide*\. In the **Inputs** section, the first item \(ingest endpoint\) always maps to pipeline 0 in the MediaLive channel, and the second item always maps to pipeline 1\.
+ The output is delivered to MediaPackage using WebDAV\. The output is always a live stream, not a VOD stream\.
+ The output name or names are automatically set to `Output n`, where n is an integer starting at 1\. 
+ The `nameModifier` for each output is automatically set to match the output name\.

**Container**
+ The codec specification is RFC 4281\. The player device might use this information\.
+ The program date time \(PDT\) period is set to 1 second\.
+ The PAT interval is set to 0, which means a single PAT is inserted at the beginning of each segment\.
+ The PMT interval is set to 0, which means a single PMT is inserted at the beginning of each segment\.

**Resiliency**
+ Resiliency is handled as follows\. If input into MediaLive is lost, then the behavior is for MediaLive to pause delivery\. MediaPackage expects this behavior and handles the loss by switching to the other input\.

**SCTE\-35**
+ Passthrough of SCTE\-35 messages is always enabled\. If you don't want SCTE\-35 markers in the outputs, you can remove them in the MediaPackage channel\. For information about SCTE\-35 handling in a MediaPackage output, see [SCTE\-35 message processing](scte-35-message-processing.md)\.

**ID3**
+ ID3 metadata is enabled\.
+ The ability to insert ID3 markers through the output group is disabled\. However, you can set up to pass through ID3 markers that are in the input, and you can insert ID3 markers using the MediaLive schedule\. For information about ID3 handling in a MediaPackage output, see [Working with ID3 metadata](id3-metadata.md)\.
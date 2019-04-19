# Fields for the HLS Group<a name="hls-group-fields"></a>

You must provide information about the destination and the structure and contents of the manifest for each HLS output group\. This destination and manifest information applies to all the outputs in the individual HLS output group\.

## HLS Group Destinations<a name="hls-destinations"></a>

For the destination URLs, specify two destinations when the channel is set up as a [standard channel](channel-class.md), or one destination when it is set up as a single\-pipeline channel\. 

The URL is one piece of the information that is used for the [destination and file names](about-hls-file-locations.md) of the manifest and media files\. 

## HLS Settings<a name="hls-settings"></a>
+ For **Name**, enter a name for the output group\. For example, **Sports Game 10122017 ABR** or **tvchannel59**\.
+ For **CDN settings**, set the value to specify the type of connection that is being used to write to the destination URLs \(specified in [HLS Group Destinations](#hls-destinations)\)\. The options are the following:
  + **Hls basic put**: To send to a content delivery network \(CDN\) that uses HTTP or HTTPS `PUT`\. Or to send to an Amazon S3 bucket \(`s3://` or `s3ssl://`\)\.
  + **Hls media store**: To send to an MediaStore container \(`mediastoressl://`\)\.
  + **Hls akamai**: To send to an Akamai CDN \(this always uses HTTP or HTTPS\)\.
  + **Hls webdav**: To send to AWS Elemental MediaPackage\. Or to send to a downstream system that uses HTTP WebDAV or HTTPS WebDAV\. 

  When you select the CDN type, more fields appear, appropriate to the type of connection\. For details about a field, choose the **Info** link next to the field\. 

  The CDN is one piece of the information that is used for the [destination and file names](about-hls-file-locations.md) of the manifest and media files\. 
+ Optionally change the value of **Input loss action**\. This field applies only if you have set up the channel as a standard channel\. It is ignored for a single\-pipeline channel; no switching occurs\.

  If you're sending output to AWS Elemental MediaPackage, set this field to match how you set the [channel class](channel-class.md):
  + If the channel is a standard channel \(to support input redundancy on AWS Elemental MediaPackage\), set this field to **PAUSE\_OUTPUT**\. With this setup, if MediaLive stops producing output on one pipeline, MediaPackage detects the lack of content on its current input and switches to the other input\. Content loss is minimized\. \(If you set this field to **EMIT\_OUTPUT**, MediaLive sends filler frames to MediaPackage\. MediaPackage doesn't consider filler frames to be lost content, and therefore doesn't switch to its other input\.\)
  + If the channel is a single\-pipeline channel, set this field to **EMIT\_OUTPUT**\. In this way, if the pipeline fails in MediaLive then AWS Elemental MediaPackage continues delivering to its own downstream system \(although the content will be filler frames\)\. If you set this field to **PAUSE\_OUTPUT**, AWS Elemental MediaPackage stops updating its endpoint, which might cause problems at the downstream system\.

  For other destinations, the appropriate value for this field depends on the behavior of the downstream system\.
+ Complete the **Caption language mappings** fields only if your plan is to include at least one embedded captions asset in the output in this output group\. See [HLS Manifests \(Embedded Captions\)](set-up-the-hls-manifest.md)\.

## HLS Outputs<a name="hls-outputs"></a>

This section contains fields that are related to the encoding of the video, audio, and captions in the output, and that are related to the packaging and delivery of the output\. 

If you want more than one output in this output group, choose **Add output**\. An **Output** line is added for each output\. Setup of the individual outputs is described in [Step 6: Create Outputs](creating-a-channel-step5.md)\.

For the **Name modifier** field for each output, enter a modifier, if appropriate\. For uses for this field, see [About HLS Group Destinations and File Names](about-hls-file-locations.md)\. 

## Location<a name="hls-location"></a>

Complete this section to specify the location and organization of the manifest and asset files at the publishing point\. The fields in this section provide some of the information that is used for the [destination and file names](about-hls-file-locations.md) of the manifest and media files\. 

## Manifests and Segments<a name="hls-manifests"></a>

Complete this section to change the default setup of the HLS manifest and the segmentation of outputs\.

## DRM<a name="hls-drm"></a>

Complete this section only if you are setting up for DRM using a static key to encrypt the output\. In **Key provider** settings, choose **Static key**, and then complete all the other fields as appropriate\. For details about a field, choose the **Info** link next to the field\. 

In a static key setup, you enter an encryption key in this section \(along with other configuration data\) and then give that key to the other party \(for example, by sending it in an email\)\. A static key is not really a DRM solution and is not highly secure\.

MediaLive supports only a static key as an encryption option\. To use a DRM solution with a key provider, you must deliver the output to AWS Elemental MediaPackage \(in other words, set up AWS Elemental MediaPackage as the destination for the output\) and then encrypt the video using AWS Elemental MediaPackage\. For more information, see the [AWS Elemental MediaPackage User Guide](https://docs.aws.amazon.com/mediapackage/latest/ug/what-is.html)\. 

## Ad Markers<a name="hls-ad-markers"></a>

Complete this section if you want to include SCTE\-35 ad messages in the output\. See [SCTE\-35 Message Processing](scte-35-message-processing.md) and specifically [Enabling Decoration – HLS](procedure-to-enable-decoration-hls.md)\.

## Captions<a name="hls-captions"></a>

If your plan is to include at least one embedded captions asset in the output in this output group, then you can optionally set up the HLS manifest to include information about the captions languages\. See [HLS Manifests \(Embedded Captions\)](set-up-the-hls-manifest.md)\.

## ID3<a name="hls-id3"></a>

You can use these fields to insert timed ID3 metadata into all the outputs in this output group\. For detailed information, see [Inserting ID3 Metadata When Creating the Channel](insert-timed-metadata.md)\.
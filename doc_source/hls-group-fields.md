# Fields for HLS Group<a name="hls-group-fields"></a>

## HLS Destinations<a name="hls-destinations"></a>

You must specify the destination URLs for this output\. You must specify two destination URLs because AWS Elemental MediaLive works in redundant mode for outputs: it requires two destinations\. 

The URL is one piece of the information used for the location and filenames of the manifest and media files\. 

## HLS Outputs<a name="hls-outputs"></a>

This section contains fields related to the encoding of the video, audio, and captions in the output, and related to the packaging and delivery of the output\. 

+ Choose **Add output** if you want more than one output in this output group\. An **Output** line is added for each output\. Setup of the individual outputs is described in [[ERROR] BAD/MISSING LINK TEXT](creating-a-channel-step5.md)\.

+ In the **Name modifier** field for each output, enter a modifier, if appropriate\. See [[ERROR] BAD/MISSING LINK TEXT](#about-hls-file-locations) for uses for this field\.

## About HLS Destinations and Filenames<a name="about-hls-file-locations"></a>

HLS output consists of a manifest, one rendition manifest for each output in the output group, and media files: one set of \.ts files for each output, and optionally one or more captions files for each output\. 

For example, one manifest file called `curling.m3u8`, one rendition manifest called `curling_high.m3u8`, and many `.ts` files containing the video and audio \(each file containing one segment of a specified number of seconds\) and three `.vtt` files for English, French, and Spanish Web\-VTT captions\.

The location of these files is controlled by several fields in the HLS output group and the individual outputs:

+ The fields in the **CDN** section\. 

  The main field specifies the type of connection to the CDN, which is the downstream system that is the destination for the HLS output\. For example, the CDN is of type HLS WebDAV if the destination is AWS Elemental MediaPackage\. The other fields in this section provide connection details\.

+ The two **URL** fields in the **HLS destinations** section\. 

  The URL consists of a *protocol* portion, a *path *portion and a *base filename *portion\. 

  For example, assume the URL is `https://sports/curling`\.

  `https://` is the protocol portion\. The protocol is required and must be correct for the CDN you specified\. For example, **https://** is correct if the CDN type is **Hls basic put** or **Hls akamai** or **Hls webdav**\. 

  + `http://` or `https://` if you selected **Hls basic put** as the CDN and you are sending to send to a CDN that uses HTTP \(or HTTPS\) PUT\. 

  + `s3://` or `s3ssl://` if you selected **Hls basic put** as the CDN and you are sending to send to an AWS S3 bucket\.

  + `mediastoressl://` if you selected **Hls media store** as the CDN\. 

  + `http://` or `https://` if you selected **Hls akamai** as the CDN\.

  + `http://` or `https://` if you selected **Hls webdav** as the CDN and you are sending to a server using WebDAV or you are sending to AWS Elemental MediaPackage\.

  `sports/` is the path portion\. The path is required and consists of the folders, terminated by a slash\. It identifies the location of the manifest and media files\. 

  `curling` is the base filename\. It is used in the manifest filenames and media filenames\. The base filename is optional\. If you omit it, AWS Elemental MediaLive uses the name of the input as the base filename\.

+ The **Name modifier **field in the **HLS outputs **section\. 

  Required only in output groups with more than one output\. For example, **\_high**\. Used in the rendition manifest filenames and in media filenames\. 

  For example, following from the example above, the manifest file would be `curling`, rendition manifest files would be `curling_high` and `curling_low`\. Media video files would by `curling_high.00001.ts`, `curling_high.00002.ts`, and so on for output 1, and `curling_medium.00001.ts`, `curling_medium.00002.ts`, and so on for output 2\. 

+ The **Segment modifier** field in the **Output settings** section of each individual output\. 

  Always optional\. For example, **\_high**\. Used only in the media filenames\. Typically used instead of **Name modifier**, when you have only one output in the output group and you want a modifier in the media but not in the manifest\. 

  For example, following from the example above, the manifest file would be `curling`, the rendition manifest file would be `curling`, and media video files would by `curling_high.00001.ts`, `curling_high.00002.ts`\. 

+ The **Base URL manifest** field and **Base URL** field in the **Location **section\. 

  Always optional\. These fields are typically used only for non\-standard manifests\.

+ The **Directory structure** field in the **Location** section\. 

  Optional\. Used only to create subdirectories for the media files\. Creates one subdirectory for each output, then creates sub\-subdirectories according to the Segments per subdirectory field\. 

  For example, the high\-resolution media files would go in subdirectories with the same name as each rendition manifest: `curling_high` and `curling_low`\. Inside each subdirectory would be a sub\-subdirectory named `00001` \(for the first set of media files\), `00002` \(for the next set of media files\), and so on\.
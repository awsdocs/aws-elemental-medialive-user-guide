# About HLS Group Destinations and File Names<a name="about-hls-file-locations"></a>

HLS output consists of a manifest, one rendition manifest for each output in the output group, and media files: one set of `.ts` files for each output, and optionally one or more captions files for each output\. 

For example, one manifest file called `curling.m3u8`, one rendition manifest called `curling_high.m3u8`, and many `.ts` files that contain the video and audio \(each file contains one segment of a specified number of seconds\) and three `.vtt` files for English, French, and Spanish WebVTT captions\.

Several fields in the **HLS group** section and the individual outputs control the location of these files:
+ The **CDN settings** fields in the **HLS settings** section\. 

  The main field specifies the type of connection to the content delivery network \(CDN\), which is the downstream system that is the destination for the HLS output\. For example, if the destination is AWS Elemental MediaPackage, the CDN is of type **hls webdav**\. The other fields in this section provide connection details\.
+ The two **URL** fields in the **HLS group destinations** section\. 

  The URL consists of a *protocol* portion, a *path *portion, and a *base filename* portion\. 

  For example, assume that the URL is `https://sports/curling`\.

  The protocol portion is `https://`\. The protocol is required and must be correct for the CDN that you specify\. For example, **https://** is correct if the CDN type is **Hls basic put** or **Hls akamai** or **Hls webdav**: 
  + `http://` or `https://` if you select **Hls basic put** in the **CDN** field and you are sending to a CDN that uses HTTP or HTTPS `PUT`
  + `s3://` or `s3ssl://` if you select **Hls basic put** in the **CDN** field and you are sending to an Amazon S3 bucket
  + `mediastoressl://` if you select **Hls media store** in the **CDN** field
  + `http://` or `https://` if you select **Hls akamai** in the **CDN** field
  + `http://` or `https://` if you select **Hls webdav** in the **CDN** field and you are sending to a server using WebDAV or you are sending to AWS Elemental MediaPackage

  The path portion is `sports/`\. The path is required and consists of the folders, terminated by a slash\. It identifies the location of the manifest and media files\. 

  The base file name is `curling`\. It is used in the manifest file names and media file names\. The base file name is optional\. If you omit it, MediaLive uses the name of the input as the base file name\.
+ The **Name modifier** field in the **HLS outputs** section\. 

  Required only in output groups with more than one output\. For example, **\_high**\. Used in the rendition manifest file names and in media file names\. 

  Following from our example, the manifest file would be `curling`, and the rendition manifest files would be `curling_high` and `curling_low`\. The media video files would be `curling_high.00001.ts`, `curling_high.00002.ts`, and so on for output 1, and `curling_medium.00001.ts`, `curling_medium.00002.ts`, and so on for output 2\. 
+ The **Segment modifier** field in the **Output settings** section of each individual output\. 

  Always optional\. For example, **\_high**\. Used only in the media file names\. Typically used instead of **Name modifier**, when you have only one output in the output group and you want a modifier in the media but not in the manifest\. 

  Following from our example, the manifest file would be `curling`, the rendition manifest file would be `curling`, and the media video files would be `curling_high.00001.ts` and `curling_high.00002.ts`\. 
+ The **Base URL manifest** field and **Base URL** field in the **Location** section\. 

  Optional\. These fields are typically used only for non\-standard manifests\.
+ The **Directory structure** field in the **Location** section\. 

  Optional\. Used only to create subdirectories for the media files\. Creates one subdirectory for each output, and then creates sub\-subdirectories according to the **Segments per subdirectory** field\. 

  For example, the high\-resolution media files will go in subdirectories with the same name as each rendition manifest: `curling_high` and `curling_low`\. Inside each subdirectory there will be a sub\-subdirectory named `00001` \(for the first set of media files\), `00002` \(for the next set of media files\), and so on\.
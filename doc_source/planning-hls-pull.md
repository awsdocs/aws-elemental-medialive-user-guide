# HLS Pull<a name="planning-hls-pull"></a>
+ MediaLive works with redundant sources, so you provide two video streams\. For optimized redundancy, MediaLive runs each source on different encoder pipelines in different Availability Zones\. You don't have to set up these Availability Zones because MediaLive does it for you\.
+ Make sure that the two streams are identical in terms of resolution and bitrate\.
+ The sources can be encrypted or unencrypted\. For information on setting up encrypted content, see later in this section\.
+ For a pull input, keep in mind that the video source must be ready to be pulled before you start the channel\. This rule applies for both HLS VOD inputs and HLS live inputs\.

## Handling Encrypted Source Content<a name="planning-hls-input-encrypted"></a>

MediaLive can ingest an HLS input that is encrypted according to the HTTP Live Streaming specification\. MediaLive supports AES\-128 but not AES\-SAMPLE\. MediaLive supports encryption using either static or rotating keys\.

### How Decryption Works<a name="hls-input-encrypted-how-it-works"></a>

The content owner sets up the main manifest to include the \#EXT\-X\-KEY with the method \(AES\-128\), the URL to the license server, and the initialization vector \(IV\)\. The content owner places the HLS manifests on the upstream system \(an HTTP\(S\) server, an AWS Elemental MediaStore container, or an Amazon S3 bucket\), and places the encryption key on the license server\. When the channel that contains this input starts, MediaLive obtains the main manifest, reads the \#EXT\-X\-KEY tag for the URL of the encryption key, and obtains the encryption key from that location\. MediaLive decrypts the input using the encryption key and the IV\. 

### Get Ready<a name="hls-input-encrypted-ready"></a>

Contact the owner of the upstream system and verify that:
+ The content is encrypted with AES\-128\.
+ The manifest includes the \#EXT\-X\-KEY tag with these attributes:
  + The `METHOD` attribute specifies AES\-128
  + The URL specifies the license server for the encryption key\.
  + The IV is blank or specifies the IV to use\. If the IV is blank, MediaLive uses the value in EXT\-X\-MEDIA\-SEQUENCE tag as the IV\.
+ If both the upstream system and the license server require authentication credentials \(user name and password\), make sure that the same credentials are used on both servers\. MediaLive does not support having different credentials for these two servers\.

After you have ensured the upstream system has set up correctly, there is no further setup for you to perform\. There is no special setup to perform in the input or in the channel\. When the channel starts, MediaLive will read the manifest and determine from the \#EXT\-X\-KEY that the input is encrypted\. It will follow the process described earlier in this section to decrypt the content as it is ingested\.
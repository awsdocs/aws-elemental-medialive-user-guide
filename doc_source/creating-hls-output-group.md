# Creating an HLS Output Group<a name="creating-hls-output-group"></a>

Follow these steps if, when you were planning the channel, you determined that you want to include an HLS output group\.

1. On the **Create channel** navigation pane, go to the** Output groups** section and choose **Add**\. The content pane changes to show the **Add output** group section\. 

1. Choose **HLS** and choose **Confirm**\. More sections appear\. 

1. Complete the fields as described in [[ERROR] BAD/MISSING LINK TEXT](hls-group-fields.md)\. 

1. When you have entered all the information for one output group, create another output group, if desired\. Otherwise, go to the next step\.

## HLS Settings<a name="hls-settings"></a>

+ Enter a name for the output group\. For example, **Sports Game 10122017 ABR** or **tvchannel59**\.

+ In **CDN settings**, set the value to specify the type of connection that is being used to write to the destination URLs \(specified in the HLS destinations section lower down on this panel\)\. The options are:

  + **Hls basic put**: To send to a CDN that uses HTTP \(or HTTPS\) PUT\. Or to send to an AWS S3 bucket \(`s3://` or `s3ssl://`\)

  + **Hls media store**: An AWS Elemental MediaStore container \(`mediastoressl://`\)\.

  + **Hls akamai**: An Akamai CDN \(this always uses HTTP or HTTPS\)\.

  + **Hls webdav**: A CDN that uses HTTP or HTTPS WebDAV\. AWS Elemental MediaPackage can be the destination for HLS output; it uses WebDAV\.

  When you have selected the CDN type, more fields appear, appropriate to the type of connection\. For details on a field, choose the Info link next to the field\. 

  The CDN is one piece of the information used for the location and filenames of the manifest and media files\. 

+ Change the value of **Input loss action**, if desired\. 

+ Complete the **Caption language mappings **fields only if the output includes embedded captions\. 

+ Complete the **Location** section to specify the location and organization of the manifest and asset files at the publishing point\. The fields in this section work with the fields in the HLS destinations\.

+ Complete the **Manifest and segments **section to change the default setup of the HLS manifest and the segmentation of outputs\.

+ Complete the **DRM** section only if you are setting up for DRM using a static key to encrypt the output\. In **Key provider **settings, choose **Static key** and complete all the other fields as appropriate\. For details on a field, choose the Info link next to the field\. 

  In a static key setup, you enter an encryption key in this section \(along with other configuration data\) and then give that key to the other party \(for example, by sending it in an email\)\. Static key is not really a DRM solution and is not particularly secure\.

  AWS Elemental MediaLive supports only static key as an encryption option\. To use a DRM solution with a key provider, you must deliver the output to AWS Elemental MediaPackage \(in other words, set up AWS Elemental MediaPackage as the destination for the output\) and then encrypt the video using AWS Elemental MediaPackage \. See the documentation for AWS Elemental MediaPackage\. 

+ Complete the **Ad marker** section if you are including SCTE\-35 ad messages in the output\. See [[ERROR] BAD/MISSING LINK TEXT](scte-35-message-processing.md) and specifically [[ERROR] BAD/MISSING LINK TEXT](procedure-to-enable-decoration-hls.md)\.

+ Complete the **Captions** section\. 

+ Complete the **ID3** section if applicable\.
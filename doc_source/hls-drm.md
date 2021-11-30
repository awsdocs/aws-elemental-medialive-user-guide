# Fields for DRM<a name="hls-drm"></a>

Complete the **DRM **section only if you are setting up for DRM using a static key to encrypt the output\. 
+ In **Key provider** settings, choose **Static key**\.
+ Complete the other fields as appropriate\. For details about a field, choose the **Info** link next to the field\. 

In a static key setup, you enter an encryption key in this section \(along with other configuration data\) and then give that key to the other party \(for example, by sending it in an email\)\. A static key is not really a DRM solution and is not highly secure\.

MediaLive supports only a static key as an encryption option\. To use a DRM solution with a key provider, you must deliver the output to AWS Elemental MediaPackage, by creating a[ MediaPackage output group](creating-mediapackage-output-group.md) instead of an HLS output group\. You then encrypt the video using MediaPackage\. For more information, see the AWS Elemental MediaPackage User Guide\. 
# Trick\-play track via I\-frames<a name="trick-play-i-frames"></a>

In an HLS output group, you can support trick\-play track by providing an I\-frame\-only manifest\.

## How the method works<a name="trick-play-iframe-how-it-works"></a>

When you create the HLS output group, you create one or more video outputs, in the usual way\. For a reminder of the output group structure, look at the diagrams in [Organize encodes in an HLS or MediaPackage output group](design-hls-package.md)\. In the output group, you enable the field to create an I\-frame\-only manifest that conforms to the HLS specification\. 

MediaLive produces two child manifests for each encode—one manifest for handling the video in the usual way, and the I\-frame\-only manifest\. The I\-frame\-only manifest lets the downstream player identify specific video frames to request, to construct the trick\-play track\. So this trick\-play track method doesn't produce additional encodes in the output group\. 

Each I\-frame\-only manifest contains the following:
+ One `#EXT-X-I-FRAMES-ONLY `tag, to indicate that the manifest is I\-frame\-only\.
+ Many `#EXT-X-BYTERANGE `entries\. Each entry identifies the position of an I\-frame position\.

## Setting up<a name="trick-play-iframe-procedure"></a>

You set up the trick\-play track once for the entire HLS output group\.

**Note**  
The information in this section assumes that you are familiar with the general steps for [creating a channel](creating-channel-scratch.md)\.

**To set up an I\-frame\-only manifest**

Include these steps when you create the HLS output group\. 

1. In the **HLS output group**, in **Manifest and segments**, for **I\-frame only playlists**, choose **ENABLED**\.

1. Set up the remaining fields in the output group [as you normally would](creating-hls-output-group.md)\. Set up the video, audio, and captions outputs and encodes [as you normally would](creating-a-channel-step6.md)\.
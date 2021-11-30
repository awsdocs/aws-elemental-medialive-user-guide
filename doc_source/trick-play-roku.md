# Trick\-play track via the Image Media Playlist specification<a name="trick-play-roku"></a>

In an HLS or MediaPackage output group, you can support a trick\-play track  by providing an asset that follows the Image Media Playlist specification, version 0\.4\. The MediaLive implementation follows the time\-based method of the specification\. The specification is located here:

[https://github.com/image-media-playlist/spec/blob/master/image_media_playlist_v0_4.pdf](https://github.com/image-media-playlist/spec/blob/master/image_media_playlist_v0_4.pdf)

Roku is one example of a platform that implements this specification\.

## How the method works<a name="trick-play-roku-how-it-works"></a>

When you create the output group, you create standard outputs in the usual way for the video, audio, and captions encodes\. See [Organize encodes in an HLS or MediaPackage output group](design-hls-package.md) for diagrams that illustrate the structure of the encodes in the output group\. 

You also create one output that contains one frame capture encode\. The encode is a series of JPEG files, one file for every video segment, which means that the capture follows the segmentation of the video encode\. This encode is the asset that the downstream player can use to implement the trick\-play track\. 

MediaLive creates a main manifest and child manifests in the usual way\. The main manifest includes an `EXT-X-IMAGE-STREAM-INF` tag for the frame capture encode\. The child manifest for the frame capture encode contains `EXT-X-IMAGES-ONLY` tags\. The contents and format of these tags comply with the Image Media Playlist specification\.

## Setting up<a name="trick-play-roku-procedure"></a>

You set up the trick\-play track in the  output group by creating an additional output that contains a video encode consisting of frame captures\. You can add up to three frame capture outputs in one output group, and up to three frame capture encodes in the channel\.

**Note**  
The information in this section assumes that you are familiar with the general steps for [creating a channel](creating-channel-scratch.md)\.

**To set up the frame capture encode in an HLS output group**

To create a frame capture encode in an HLS output group, you create a special type of output and set its video codec to **Frame Capture**\.

1. In the **HLS output group**, in **HLS outputs**, choose **Add output** to add another output\.

1. For that output, choose **Settings**, and in **Output settings**, set **HLS settings** to **Frame capture hls**\.

1. In **Stream settings**, choose **Video** and set up the video fields, including:
   + **Width** and **Height** – Contact your downstream system to obtain the correct values\. If you guess at the values, the experience on the downstream player might not be optimal\.
   + **Codec settings** – Choose **Frame capture**\. 
   + **Capture interval** – Don't change the value of this field\. Leave it empty, so that the frame capture uses the default interval\.

1. Choose **Audio 1** and choose **Remove audio** so that the container has only one encode \(a video encode\)\.

**To set up the frame capture encode in a MediaPackage output group**

To create a frame capture encode in a MediaPackage output group, you create a regular output and set its video codec to **Frame Capture**\.

1. In the **MediaPackage output group**, in **MediaPackage outputs**, choose **Add output** to add another output\.

1. For that output, choose **Settings**, and then choose **Stream settings**\. In **Stream settings**, choose **Video**\. 

1. In **Codec settings**, choose **Frame capture**\. 

1. Set up the other video fields, including:
   + **Width** and **Height** – Contact your downstream system to obtain the correct values\. If you guess at the values, the experience on the downstream player might not be optimal\.
   + **Capture interval** – Don't change the value of this field\. Leave it empty, so that the frame capture uses the default interval\.

1. Choose **Audio 1** and choose **Remove audio** so that the container has only one encode \(a video encode\)\.

The output is part of the ABR stack and has the same destination as the other encodes in the HLS or MediaPackage output group\.
# Fields for the HLS container<a name="hls-container"></a>

The following fields configure the container in each output\.
+ **HLS outputs** –** Output settings **– **HLS settings** section

These fields control the content of the manifest and structure of the segments\. By comparison, fields described in [Fields for contents of manifests](hls-manifest-contents.md) control how many manifests and segments are in the output\.

**To configure the container**

1. In **HLS Settings**, choose the appropriate option\. For information on the options, see the list after this procedure\.

1. For **Standard hls**, more fields appear\. Choose **Transport/container configuration** and **PID settings**\. More fields appear\.

1. Change any fields\. Typically, you change the fields in these two sections only if the downstream system provides you with values\.

**About HLS containers**

MediaLive supports these types of containers:
+ **Standard hls** – Choose this type of container if you want to package the streams \(encodes\) in a transport stream \(TS\)\. Choose this container type for all the outputs in the output group \(except for outputs that are part of an audio rendition group\)\. Each output might contain these encodes:
  + One video encode
  + One video encode with embedded captions
  + One video encode \(and optionally embedded captions\) and one or more audio encodes
  + One captions encode
+ **Fmp4 hls** – Choose this type of container if you want to package the streams \(encodes\) as fragmented MP4\. Choose this container type for all the outputs in the output group \(except for outputs that are part of an audio rendition group\)\. Each output might contain these encodes:
  + One video encode
  + One video encode with embedded captions
  + One captions encode
+ **Audio\-only** – Choose this type of container for each audio\-only output that is part of an audio rendition group\. The rendition group can be part of a TS \(transport stream\) or part of an fMP4 package\. For information about creating an audio rendition group, see [Audio rendition groups for HLS](audio-renditions.md)\.
+ **Frame capture** – Choose this type of container to create a JPEG file of frame captures in the output group\. This container is used to implement trick\-play\. For more information about this feature and for instructions on setting it up in the channel, see [Trick\-play track via the Image Media Playlist specification](trick-play-roku.md)\.
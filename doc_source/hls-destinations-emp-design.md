# Step 1: Design the path for the output destination<a name="hls-destinations-emp-design"></a>

Perform this step if you haven't yet designed the full destination path or paths\. If you've already designed the paths, go to [Step 2: Complete the fields on the console](hls-specify-destination-emp.md)\.

**To design the path**

1. Collect the information you [previously obtained](origin-server-hls-emp.md) from the MediaPackage user:
   + The two URLs \(input endpoints is the MediaPackage terminology\) for the channel\. The two URLs for a channel look like this:

     `6d2c.mediapackage.uswest-2.amazonaws.com/in/v2/9dj8/9dj8/channel` 

     `6d2c.mediapackage.uswest-2.amazonaws.com/in/v2/9dj8/e333/channel`

     where:

     `6d2c.mediapackage.uswest-2.amazonaws.com` is the domain

     `/in/v2/9dj8/9dj8/` is the folders

     `channel` is the base file name for all the files for this destination\. Note that with MediaPackage, the base file name is always *channel*, for every output\.

     The two URLs are always identical except for the folder just before `channel`\.

     Make sure that you obtain the URLs, not the channel name\.
   + The user name and password\. MediaPackage always requires user authentication\.

1. You must design the portions of the destination paths that follow the URLs\. 

**Topics**
+ [The syntax for the paths for the outputs](#hls-syntax-emp)
+ [Designing the nameModifier](#hls-nameModifier-design-emp)
+ [Designing the segmentModifier](#hls-segmentModifier-design-emp)

## The syntax for the paths for the outputs<a name="hls-syntax-emp"></a>

An HLS output always includes three categories of files: 
+ The main manifest
+ The child manifests
+ The media files

The following table describes the parts that make up the destination paths for these three categories of files\.

The destination paths for these three categories of files are identical up to and including the *baseFilename*, which means thatMediaLive sends all these categories of files to the same folder\. The modifiers and file extensions are different for each category of file\. When sending to MediaPackage, you must send all the files to the same folder\. The downstream systems expect all the files to be together\.


| File | Syntax of the path | Example | 
| --- | --- | --- | 
| Main manifest files | protocol channelURL extension | The path for output:https://6d2c\.mediapackage\.uswest\-2\.amazonaws\.com/in/v2/9dj8/9dj8/channel\.m3u8 | 
| Child manifest files | protocol channelURL nameModifier extension | The path for the child manifest for the high\-resolution renditions of the curling output`https://6d2c.mediapackage.uswest-2.amazonaws.com/in/v2/9dj8/9dj8/channel-high.m3u8` | 
| Media files \(segments\) | protocol channelURL nameModifier optionalSegmentModifier counter extension | The path for the file for the 230th segment might be:https://6d2c\.mediapackage\.uswest\-2\.amazonaws\.com/in/v2/9dj8/9dj8/channel\-high\-00230\.ts | 

These paths are constructed as follows:
+ The MediaPackage user should have provided you with the channel URLs\. The URLs cover the portion of the path up to and including the baseFilename\.
+ You must determine the following:
  + The modifier
  + The segmentModifier

  See the sections that follow\.
+ MediaLive inserts the underscore before the counter\.
+ MediaLive generates the counter, which is always five digits starting at 00001\.
+ MediaLive inserts the dot before the extension\.
+ MediaLive selects the extension:
  + For manifest files – always` .m3u8`
  + For media files – \.ts for files in a transport stream, or \.mp4 for files in an fMP4 container 
+ For an output that contains video \(and possibly other streams\), you typically describe the video\. For example, **\-high** or **\-1920x1080\-5500kpbs** \(to describe the resolution and the bitrate\)\.
+ For an output that contains only audio or only captions, you typically describe the audio or captions\. For example, **\-aac** or **\-webVTT**\.
+ It’s a good idea to start the `nameModifier` with a delimiter, such as a hyphen, in order to separate the` baseFilename` from the `nameModifier`\.
+ The `nameModifier` can include [data variables](variable-data-identifiers.md)\.

## Designing the nameModifier<a name="hls-nameModifier-design-emp"></a>

Design the `nameModifier` portions of the file name\. The child manifests and media files include this modifier in their file names\. This `nameModifier` distinguishes each output from the other, so it must be unique in each output\. Follow these guidelines:

## Designing the segmentModifier<a name="hls-segmentModifier-design-emp"></a>

Design the segmentModifiers portion of the destination path\. The segmentModifier is optional, and if you include it, only the media file names include it\. 

A typical use case for this modifier is to use a data variable to create a timestamp, to prevent segments overriding each other if the channel restarts\. For example, assume that you include the timestamp **$t$\-**\. Segment 00001 might have the name `curling-120028-00001`\. If the output restarts a few minutes later \(which causes the segment counter to restart\), the new segment 00001 will have the name `curling-120039-00001`\. The new file won't overwrite the file for the original segment 00001\. Some downstream systems might prefer this behavior\.
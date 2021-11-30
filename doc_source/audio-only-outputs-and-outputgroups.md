# Output groups and outputs<a name="audio-only-outputs-and-outputgroups"></a>

## Setting up output groups<a name="audio-only-opg"></a>

You can create an audio\-only output in the following types of output groups\.
+ HLS
+ Microsoft Smooth
+ RTMP
+ UDP

## Setting up outputs<a name="audio-only-outputs"></a>

The following list describes the number and type of required outputs, based on the output group\.

**HLS output group**  
Create outputs in the output group as follows:
+ If the output group contains *only one audio encode*, then create one output\. Set the container type to **Audio\-only**\. 
+ If the output group contains *more than one audio encode*, then set up an audio rendition group that doesn't include video\. See [Audio rendition groups for HLS](audio-renditions.md)\.

**Microsoft Smooth output group**  
Create one output for each audio encode\. 

**RTMP output groups**  
Create one output for the single audio encode\. \(RTMP always supports only one audio in each output group\.\)

**UDP output groups**  
Create one output for all the audio encodes\.
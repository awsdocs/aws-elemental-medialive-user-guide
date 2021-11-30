# Summary of encode rules for output groups<a name="encode-rules"></a>

 This table summarizes the rules for encodes for each output group\. In the first column, find the output you want, then read across the row\.


****  

| Type of output group | Rule for video encodes | Rule for audio encodes | Rule for captions encodes | 
| --- | --- | --- | --- | 
| Archive | One video encode\. | Zero or more audio encodes\. | Zero or more captions encodes\. The captions are either embedded or object\-style captions\. | 
| Frame Capture | One video encode\. | Zero audio encodes\. | Zero captions encodes\. | 
| HLS or MediaPackage | One or more video encodes\. Typically, there are multiple video encodes\. | Zero or more audio encodes\. Typically, there are multiple audio encodes\.  | Zero or more captions encodes\. Typically, there are caption languages to match the audio languages\. The captions are either embedded or sidecar captions\. | 
| Microsoft Smooth | One or more video encodes\. Typically, there are multiple video encodes\. | Zero or more audio encodes\. Typically, there are multiple audio encodes\.  | Zero or more captions encodes\. Typically, there are caption languages to match the audio languages\. The captions are always sidecar captions\. | 
| RTMP |  One video encode\.  | Zero or one audio encodes\.  | Zero or one caption encodes\. The captions are either embedded or object\-style captions\. | 
| UDP |  One video encode\.   | One or more audio encodes\.  | One or more captions encodes\. The captions are either embedded or object\-style captions\. | 

Some output groups also support audio\-only outputs\. See [Output groups and outputs](audio-only-outputs-and-outputgroups.md)\.

Some output groups also support outputs that contain JPEG files, to support trick play according to the Roku specification\. See [Trick\-play track via the Image Media Playlist specification](trick-play-roku.md)\.
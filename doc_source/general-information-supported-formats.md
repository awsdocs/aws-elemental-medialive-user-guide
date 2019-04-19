# General Information About Supported Formats<a name="general-information-supported-formats"></a>

 The following table shows the supported formats, specifies whether they are supported in inputs or outputs, and specifies the standard that defines each format\. 


| Caption | Supported in Input | Supported in Output | Description | 
| --- | --- | --- | --- | 
| Ancillary data | Yes |   | From MXF input, data that is compliant with “SMPTE 291M: Ancillary Data Package and Space Formatting” and that is contained in ancillary data\. | 
| ARIB  | Yes | Yes | Captions that are compliant with ARIB STD\-B37 Version 2\.4\. | 
| Burn\-in | N/A | Yes | From input: It is technically impossible for the encoder to read burn\-in captions\. Therefore, from an input viewpoint, they can't be considered to be captions\.For output: Burn\-in captions are captions that are converted into text and then overlaid on top of the picture directly in the video stream\. | 
| DVB\-Sub | Yes | Yes | Captions that are compliant with ETSI EN 300 743\. | 
| Embedded | Yes | Yes | Captions that are compliant with the EIA\-608 standard \(also known as CEA\-608 or SMPTE\-259M or “line 21 captions”\) or the CEA\-708 standard \(also known as EIA\-708\)\. | 
| Embedded\+SCTE\-20 | Yes | Yes | Captions that have both embedded and SCTE\-20 in the video\. The embedded captions are inserted before the SCTE\-20 captions\.  | 
| RTMP CaptionInfo |  | Yes | Captions that are compliant with the Adobe onCaptionInfo format\. | 
| RTMP CuePoint |  | Yes | Captions that are in the cuePoint format\. | 
| SCTE\-20 | Yes |   | Captions that are compliant with the standard “SCTE 20 2012 Methods for Carriage of CEA\-608 Closed Captions and Non\-Real Time Sampled Video\.” | 
| SCTE\-20\+Embedded |   | Yes | Captions that are compliant with SCTE\-43\. The SCTE\-20 captions are inserted in the video before the embedded captions\. | 
| SCTE\-27 | Yes | Yes | Captions that are compliant with the standard “SCTE\-27 \(2011\), Subtitling Methods for Broadcast Cable\.” | 
| Teletext  | Yes | Yes | From TS input: Captions in the EBU Teletext format\. | 
| TTML | Yes | Yes | Captions files that are compliant with the standard “Timed Text Markup Language 1 \(TTML1\) \(Second Edition\)\.” | 
| WebVTT |   | Yes | Captions that are compliant with “webvtt: The Web Video Text Tracks Format” \([http://dev\.w3\.org/html5/webvtt/](http://dev.w3.org/html5/webvtt/)\)\. | 
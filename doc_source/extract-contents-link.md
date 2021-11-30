# Identifying content in an AWS Elemental Link source<a name="extract-contents-link"></a>

The content in an AWS Elemental Link source is always a transport stream \(TS\) that contains one video asset and one audio pair\. It might also contain embedded\-style or object\-style captions\. 

Obtain identifying information from the content provider:
+ For video – You don't need identifying information\.
+ For audio – Obtain the languages in the tracks\. For example, "track 1 is French"\. 
+ For captions – Obtain the identifiers:
  + For embedded captions, obtain the languages in the channel numbers\. For example, "channel 1 is French"\. 
  + For Teletext captions, [if your plan for captions](assess-uss-captions.md) is to convert the captions to a different format, you must obtain the page numbers for the languages that you want to convert\. If you plan to pass through the captions as Teletext in the output, you don't need any identifiers\.

Also obtain the following information about the content:
+ The maximum bitrate\. You will have the option to throttle this bitrate when you set up the device in MediaLive\. For more information, see [Working with MediaLive devices](https://docs.aws.amazon.com/medialive/latest/ug/eml-devices.html)[Working with MediaLive devices](eml-devices.md)\. 
+ Whether the content includes an embedded timecode\. If it does, you can choose to use that timecode\. For more information, see [Timecode configuration](https://docs.aws.amazon.com/medialive/latest/ug/timecode.html)[Timecode configuration](timecode.md)\. 
+ Whether the content includes ad avail messages \(SCTE\-104 messages that MediaLive will automatically convert to SCTE\-35 messages\)\. For more information about ad avail messages, see [SCTE\-35 message processing](scte-35-message-processing.md)\.
# Nielsen watermarks<a name="feature-nielsen-watermark"></a>

AWS Elemental MediaLive can create new Nielsen watermarks and insert them into your audio\. You can also pass through and convert existing Nielsen watermarks to ID3 metadata\. For more information on passthrough and conversion to ID3, see [Converting Nielsen watermarks to ID3](feature-nielsen-id3.md)\. 

Typically, only content and distribution providers use Nielsen watermarks\. If you're not working with Nielsen to implement watermarks, you don't need to read this section\. 

Nielsen watermarking is a feature that allows you to insert watermark codes into your audio output\. The watermark is inaudible to the human ear but can be detected by Nielsen monitoring devices for tracking and measurement purposes\.

Each Nielsen watermark contains a unique identifier and a timestamp\. To configure this feature, you need information from Nielsen, such as Source Identification values and check digits\. Nielsen watermarks support CBET and NAES II/NW encoding types\. Determine which encoding types you will be using before you set up Nielsen watermarking in MediaLive\. It is possible to use both CBET and NAES II/NW\. 

**Topics**
+ [Prerequisites](#prerequisites)
+ [Supported audio](#supportedaudio)
+ [Setting up Nielsen watermarks](watermark-procedure.md)

## Prerequisites<a name="prerequisites"></a>

To configure Nielsen watermarking in MediaLive, you need one or both of the following\. Nielsen must provide you these values:

1. For Critical Band Encoding Technology \(CBET\) encoding, CBET Source Identification \(CSID\) code and CBET check digits\.

1. For NAES II or NAES NW encoding, Source Identification Code \(SID\) and check digits\.

## Supported audio<a name="supportedaudio"></a>

Use this section to ensure that your audio is supported for Nielsen watermarking\. Your audio must meet the following requirements:
+ Sample\-rate frequency of 48 kHz \(48000 samples per second\)\.
+ Up to 8 audio channels, with interleaved samples\.
+ 1, 2, 6, and 8 channel audio must conform to the format in the following table:


|  Number of channels  |  Input  |  Channel 1  |  Channel 2  |  Channel 3  |  Channel 4  |  Channel 5  |  Channel 6  |  Channel 7  |  Channel 8  | 
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
|  1  | Mono |  Left  |  N/A  |  N/A  |  N/A  |  N/A  |  N/A  |  N/A  |  N/A  | 
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
|  2  |  Stereo  |  Stereo left  |  Stereo right  |  N/A  |  N/A  |  N/A  |  N/A  |  N/A  |  N/A  | 
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
|  6  | 5\.1 audio |  Front left  |  Front right  |  Center  |  LFE  |  Surround left  |  Surround right  |  N/A  |  N/A  | 
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
|  8  |  5\.1 audio \+ stereo  |  Front left  |  Front right  |  Center  |  LFE  |  Surround left  |  Surround right  |  Stereo left  |  Stereo right  | 
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |

**Recommended minimum bitrates**

We strongly recommend following the minimum audio bitrates listed in the following table\. If you set the audio bitrates lower than the recommended values, your watermarks might not be reliably detected\.


|  Channels  |  CODEC  |  Minimum bitrate \(kbps\)  | 
| --- |--- |--- |
| Stereo | AC\-3 | 192 | 
| Stereo | EAC\-3 | 192 | 
| Stereo | AAC LC | 128 | 
| Stereo | MPEG\-1 L2 | 96 | 
| 5\.1 | AC\-3 | 384 | 
| 5\.1 | HE AAC v1 | 256 | 
| 5\.1 | EAC\-3 | 192 | 
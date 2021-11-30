# Assess the audio in the sources<a name="ips-assess-audio"></a>

MediaLive provides flexibility in extracting audio from sources in a multiple\-input channel\. It also has some special requirements for the audio in these sources\. 

**To assess the audio in the sources**

1. Read the information lower down about flexibility to get a sense of how MediaLive supports a wide variety of audio sources\.

1. Then read each of the requirements for information on specific constraints in the audio sources\. Make sure that the audio in each source meets these requirements\.

1. If you reject a source, you might want to contact the upstream system to determine if it could provide a more suitable version of the source content\. 

## Flexibility in using audio<a name="ips-audio-nonrequirements"></a>

When assessing the audio, note the following rules\. These rules provide flexibility in extracting audio, and therefore allow you to use a variety of sources:
+ Different languages in a source can use different codecs\. For example, in your sources English might be in AAC while Spanish is in MPEG\-2\.
+ The method of identifying an audio language in the source doesn't have to be the same in all the sources in the multiple\-input channel\. 

  For example, in source 1 you can identify the languages by PID\. In source 2, you can identify by language code\.

## First requirement: each language must have the same coding mode in all sources<a name="ips-audio-req-a"></a>

Each output language must be present in every source, and the coding mode must be the same in all sources\. 

For example, assume that the channel contains an Archive output group that contains one audio encode for English 2\.0 and one audio encode for French 2\.0: 
+ Assume that you have a source that contains AAC 2\.0 audio in English and Dolby Digital 5\.1 in French\. 
+ Assume that you have a second source that contains AAC 2\.0 audio in English and AAC 5\.1 audio in French\.

  For English, this source contains audio with the same codec and coding mode as the first source\. For French, it contains the same coding mode as the first source but a different codec\.

  This source is acceptable\. The fact that in a comparison of source 1 and source 2, the codecs are different for French isn't relevant\. The requirement is that the *coding modes* are the same\. 
+ Assume that you have a third source that contains AAC 2\.0 audio in English and AAC 2\.0 audio in French\. 

  This source is *not* acceptable because for French, the audio has a different coding mode from the first source\.

## Second requirement: each language must provide the highest coding mode required<a name="ips-audio-req-b"></a>

For each language, every source must include audio that can produce all the highest coding mode among all the outputs in the channel\. 

For example, assume that the channel contains an Archive output group that contains one audio encode for Spanish AAC 2\.0\. The channel also contains one HLS output group that contains one audio encode for Spanish Dolby Digital 5\.1:
+ Assume that you have an source that contains Dolby Digital 5\.1 audio in Spanish\. 

  This source contains audio that can produce all the desired output audio encodes for Spanish\. You must set up the Archive output to remix the audio down to 2\.0\. You don't need to set up the HLS output to remix the audio\.
+ Assume that you have a second source that contains AAC 2\.0 in Spanish\. 

  This source is *not* acceptable\. This source can't produce Spanish Dolby Digital 5\.1 for the HLS output\. 

## Third requirement: mp4 sources should not contain variations of the same language<a name="ips-audio-req-d"></a>

An MP4 file that contains multiple variations of a language might produce undesirable output audio\. For best results, the file should contain only one version of a language: 
+ For example, assume that one MP4 source contains AAC 5\.1 audio in English\. The channel output requires one audio encode for English 2\.0\. Therefore, in the output you set up the audio encode to down mix from 5\.1 to 2\.0\.
+ Assume that you have a second source that contains AAC 2\.0 in English in track 2, and Dolby Digital 5\.1 audio in English in track 3\. 

  MediaLive extracts audio from MP4 files by language code and it extracts from the first track that contains that language\. In this example, it extracts track 2, which contains AAC 2\.0\. It ignores track 3\. On the output side, MediaLive will try to remix this source, resulting in audio that has poor quality\. 

## Fourth requirement: all sources must contain dolby if producing passthrough encode<a name="ips-audio-req-c"></a>

If one of the outputs includes an encode that is set up with the Passthrough codec, then all the sources must include Dolby Digital, Dolby Digital Plus, or Dolby Atmos in all the required language or languages\. 

If any single source doesn't include one of these codecs, you can't use it in the multiple\-input channel\.

The Passthrough option for a codec allows for the ability to ingest audio that is in Dolby Digital, Dolby Digital Plus, or Dolby Atmos and in any coding mode, and pass it through without transcoding it\.
# Input settings—Audio selectors<a name="input-audio-selectors"></a>

If you want to extract audio from the input, this section is required\. You create one or more audio selectors to identify the audio asset to extract\. Typically, you identify different languages from the input, but you could also extract different audio codecs \(such as AAC and Dolby\)\.

You can create a maximum of 20 audio selectors in one channel\.

**To identify the audio to extract**

1. Decide if you need to create any audio selectors\. When you planned the channel, you should have [identified the audio assets](channel-map-output-source.md) that you need to extract from this input\. 

   The following table specifies whether you need to create an audio selector in order to extract that audio\. In the table, find your input type, and read the guidance\.    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/input-audio-selectors.html)

   If the input contains more than one audio asset and you don't create a selector, MediaLive selects the first audio it encounters\.

1. Choose **Add audio selector** once for each audio that you want to extract from the input\. 

1. In each audio selector, in **Audio selector name**, enter a name that describes the audio that you are extracting\.

1. In each audio selector, complete **Selector settings** as specified in the following table\. 


| Input type | How to complete Selector settings | 
| --- | --- | 
| CDI | Choose Audio track selection, then choose Add tracks to add a selector for each track you want to extract\. In each Track field, enter the track number\. | 
| Elemental Link | Leave this field blank\. | 
| HLS | Select in one of these ways:[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/input-audio-selectors.html)We recommend you select by PID\. If you select by language, MediaLive selects the first instance of that language that it encounters\. That might not be the language version you want\. | 
| MediaConnect | Select in one of these ways:[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/input-audio-selectors.html)We recommend you select by PID\. If you select by language, MediaLive selects the first instance of that language that it encounters\. That might not be the language version you want\. | 
| MP4 | Choose Audio track selection, then choose Add tracks to add a selector for each track you want to extract\. In each Track field, enter the track number\. | 
| RTMP | Leave this field blank\. | 
| RTP | Choose Audio pid selection and enter the PID for the audio asset in PID\.Or choose **Audio language selection** and enter the three\-letter ISO code for the language\.We recommend you select by PID\. If you select by language, MediaLive selects the first instance of that language that it encounters\. That might not be the language version you want\. | 
# Settings for an HLS Output<a name="output-settings-hls"></a>

## Output Settings Section<a name="hls-output-section"></a>

+ Complete the Name modifier and Segment modifier fields as described in [[ERROR] BAD/MISSING LINK TEXT](hls-group-fields.md#hls-destinations)\.

+ Set HLS Settings field as appropriate:

  + If this output is a regular output with video and audio encodes, then choose Standard HLS\. More fields appear\. Leave Audio Rendition Sets as is \(the value is ignored\), and complete the fields under M3U8 as desired; the default value is often desireable\. For details on a field, choose the Info link next to the field\.

  + If this output is an output that contains only a video encode and the output is part of an output group that includes an audio rendition group, then choose Standard HLS\. More fields appear\. Complete Audio Renditon Sets as required\. complete the fields under M3U8 as desired; the default value is often desireable\. For details on a field, choose the Info link next to the field\.

  + If this output is an output that contains only an audio encode and the output is part of an output group that includes an audio rendition group or is part of an output group that has only audio encodes \(no video at all\), then choose Audio only HLS\. A special set of fields appear for configuring the audio\. For details on a field, choose the Info link next to the field\.

## Streams Section<a name="hls-streams-section"></a>

In Stream settings, decide if you need to create more encodes for this output, based on the workflow you planned\. By default, each output is set up with one video encode and one audio encode\. Select the appropriate Add button or Delete button to set up the output with the encodes – video, audio, captions – you planned for this output\.

For example, in one output you may want one video and two audios, in another output you may want one captions, and in a third output you may want just one captions\.

See [[ERROR] BAD/MISSING LINK TEXT](creating-a-channel-step6.md), [[ERROR] BAD/MISSING LINK TEXT](creating-a-channel-step7.md), and [[ERROR] BAD/MISSING LINK TEXT](creating-a-channel-step8.md) for information on the fields in each type of encode\.
# Settings for an HLS Output<a name="output-settings-hls"></a>

In the **Output** page for an HLS output group, you provide information about the transport for this output and the video, audio, and captions encodes to create in the output\.

## Output Settings Section<a name="hls-output-section"></a>
+ For **Name modifier** and **Segment modifier**, complete the fields as described in [HLS Group Destinations](hls-group-fields.md#hls-destinations)\.
+ Set the **HLS Settings** field as appropriate:
  + If this output is a regular output with video and audio encodes, choose **Standard HLS**\. More fields appear\. Keep the default for **Audio rendition sets** \(the value is ignored\), and complete the fields under **M3U8** as needed or keep the default value, which often is a good choice\. For details about a field, choose the **Info** link next to the field\.
  + If this output is an output that contains only a video encode and the output is part of an output group that includes an audio rendition group, choose **Standard HLS**\. More fields appear\. Complete **Audio rendition sets** as required\. Complete the fields under **M3U8** as needed or keep the default value, which often is a good choice\. For details about a field, choose the **Info** link next to the field\.
  + If this output is an output that contains only an audio encode and the output is part of an output group that includes an audio rendition group or is part of an output group that has only audio encodes \(no video at all\), choose **Audio only HLS**\. A special set of fields appears for configuring the audio\. For details about a field, choose the **Info** link next to the field\.

## Streams Section<a name="hls-streams-section"></a>

In **Stream settings**, decide if you need to create more encodes for this output, based on the [workflow that you planned](planning-the-channel.md)\. By default, each output is set up with one video encode and one audio encode\. Choose the appropriate **Add** button or **Delete** button to set up the output with the encodes—video, audio, and captions—that you planned for this output\.

For example, in one output you might want one video asset and two audio assets, in another output you might want one captions asset for French captions, and in a third output you might want one captions asset for Spanish captions\. For information on why you would set up like this \(for example, with an output that contains only one captions asset\), see [Examples of Channel Designs](examples-channel-design.md)\.

For information about the fields in each type of encode, see [Step 7: Set Up the Video Encode](creating-a-channel-step6.md), [Step 8: Set Up the Audio Encodes](creating-a-channel-step7.md), and [Step 9: Set up the Captions Encodes](creating-a-channel-step8.md)\. 
# Settings for an Archive Output<a name="output-settings-archive"></a>

On the **Output** page for an Archive output group, you provide information about the container for this output, and the video, audio, and captions encodes to create in that container\.

## Output Settings Section<a name="archive-output-section"></a>
+ For **Name modifier**, enter a name as described in [Archive Destinations](archive-group-fields.md#archive-destinations)\.
+ Leave **Extension** blank; it is always set to **m2ts**\.
+ In the fields under **Container Settings**, optionally change any values\. For details about a field, choose the **Info** link next to the field\.
+ In the fields under **PID settings**, optionally change any values\. For details about a field, choose the **Info** link next to the field\.

## Streams Section<a name="archive-streams-section"></a>

In **Stream settings**, decide if you need to create more encodes for this output, based on the [workflow that you planned](planning-the-channel.md)\. By default, each output is set up with one video encode and one audio encode\. Choose the appropriate **Add** button or **Delete** button to set up the output with the encodes—video, audio, and captions—that you planned for this output\.

For example, in one output you might want one video asset and two audio assets, in another output you might want one captions asset for French captions, and in a third output you might want one captions asset for Spanish captions\. For information about why you would set up like this \(for example, with an output that contains only one captions asset\), see [Examples of Channel Designs](examples-channel-design.md)\.

For information about the fields in each type of encode, see [Step 7: Set Up the Video Encode](creating-a-channel-step6.md), [Step 8: Set Up the Audio Encodes](creating-a-channel-step7.md), and [Step 9: Set up the Captions Encodes](creating-a-channel-step8.md)\.
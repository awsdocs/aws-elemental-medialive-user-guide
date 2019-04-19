# Fields for the Microsoft Smooth Group<a name="smooth-group-fields"></a>

You must provide information about the destination for all the outputs in each Microsoft Smooth output group\.

You also must provide information about the destination for each Microsoft Smooth output group\. This destination information applies to all the outputs in the individual Microsoft Smooth output group\.

## Microsoft Smooth Settings<a name="smooth-settings"></a>
+ For **Name**, enter a name for the output group\. For example, **Sports Game 10122017 ABR** or **tvchannel59**\.
+ If you want to change the default setup of the Microsoft Smooth manifest and fragments, choose **General configuration**\. For details about a field, choose the **Info** link next to the field\.
+ If you want to change the configuration of the event information that is sent to the Microsoft IIS server, choose **Event configuration**\. For details about a field, choose the **Info** link next to the field\.
+ If you want to change the default setup of the timecode and timestamp that are used in all the outputs in this output group, choose **Timecode configuration**\. For details about a field, choose the **Info** link next to the field\.
+ If you want all the outputs in this output group to include the SCTE\-35 messages that are already present in the input, choose **Sparse track**\. The messages will be included in a sparse track\. For details about a field, choose the **Info** link next to the field\. For more information, see [SCTE\-35 Message Processing](scte-35-message-processing.md)\.

## Microsoft Smooth Group Destinations<a name="smooth-destinations"></a>

For the destinations \(A and B\), specify two destinations when the channel is set up as a [standard channel](channel-class.md), or one destination when it is set up as a single\-pipeline channel\. The URLs must use the HTTP or HTTPS protocol\. Do not include the port\. 

Specify the path portion of the destination as `/folders/basefilename`\. The `basefilename` will be used as the first part of the file name of all the files for all outputs in this output group\. Or specify it as `/folders/`\. In this case, the name of the input will be used for the file names\. 

## Microsoft Smooth Outputs<a name="smooth-outputs"></a>

The **Microsoft Smooth Outputs** section on the console contains fields that relate to the encoding of the video, audio, and captions in the output\. The section also includes fields that relate to the packaging and delivery of the output:
+ If you want more than one output in this output group, choose **Add output**\. An **Output** line is added for each output\. Setup of the individual outputs is described in [Step 6: Create Outputs](creating-a-channel-step5.md)\.
+ For the **Name modifier** field for each output, enter a modifier, if appropriate\. For uses for this field, see the [examples](smooth-examples.md)\. 
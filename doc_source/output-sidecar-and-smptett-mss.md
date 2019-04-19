# Sidecar Captions and SMPTE\-TT in Microsoft Smooth<a name="output-sidecar-and-smptett-mss"></a>

Follow this procedure if the format of the captions asset that you want to add is a sidecar, or if the format is SMPTE\-TT for a Microsoft Smooth output group\. See [ Step 3: Match Formats to Categories](categories-captions.md)\.

You set up each captions asset in its own output within the output group\.

**To set up the captions**

1. In the channel that you are creating, in the navigation pane, find the output group \(which you have already created\)\. For example, find the HLS output group\.

1. Create an output in the usual way: in the **HLS outputs** pane, choose **Add output**\. 

1. Choose the output to show the **Stream settings** pane\. The output is set up by default with one undefined video encode and one undefined audio encode\.

1. For **Stream settings**, remove the video and audio encodes from this output by choosing the encode and selecting **Remove video** or **Remove audio**\. The output is now empty\.

1. Choose **Add captions**\. You now have an undefined captions encode inside this output\.

1. For **Captions description name**, enter a name for this captions asset that is unique in the channel, for example, **Web\-VTT Czech**\. Or accept the default \(which is automatically generated\)\. 

1. For **Captions selector name**, enter the name of the captions selector that you created in [step 1](identify-captions-in-the-input.md)\. Specify the selector that identifies the captions asset that is the source for the captions in this output\.

1. For **Captions settings**, choose the appropriate format for the output captions\.

1. Complete the fields that appear for the selected format\. For details about a field, choose the Info link beside the field\. 

1. You now have one output that contains one captions encode that is fully defined\.

1. Repeat these steps to create sidecar captions in this or another output group, as applicable\.
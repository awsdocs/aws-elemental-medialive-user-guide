# All Captions Except Sidecar or SMPTE\-TT in Microsoft Smooth<a name="output-embedded-and-more"></a>

Follow this procedure if the format of the captions asset that you want to add belongs to the category of embedded, burn\-in, or object\. You set up the captions and video and audio in the same output\.

**To set up the output captions**

1. In the channel that you are creating, in the navigation pane, find the output group \(which you have already created\)\. For example, find the HLS output group\.

1. If you have already set up this output group with video and audio, find the outputs where you want to add the captions\. Or if you have not set up with video and audio, create a new output in this output group\. You set up the captions now, and then set up the video and audio later\.

1. Choose the output\.

1. For **Stream settings**, choose **Add captions**\. You now have an undefined captions encode inside this output\. 

1. For **Captions description name**, enter a name for this captions asset that is unique in the channel, for example, **Embedded**\. Or accept the default \(which is automatically generated\)\. 

1. For **Captions selector name**, enter the name of the captions selector that you created in [step 1](identify-captions-in-the-input.md)\. Specify the selector that identifies the captions asset that is the source for the captions in this output\.

1. For **Captions settings**, choose the captions format for the output captions\. 

1. Complete the fields that appear for the selected format\. For details about a field, choose the Info link beside the field\. For tips about font styles in DVB\-Sub or burn\-in, see [Font Styles for Burn\-in or DVB\-Sub Output](font-styles-for-burn-in.md)\.

1. If the output format is embedded and the output group is HLS, you can include captions language information in the manifest\. You perform this setup in the output settings \(separate from the captions encode\)\. See [HLS manifest ](set-up-the-hls-manifest.md)\.

1. If the output format is ARIB or DVB\-Sub or SCTE\-27, you must perform some extra setup in the output settings \(separate from the captions encode\)\. See [PIDS for ARIB output](complete-the-pids-for-arib.md) or [PIDs for DVB\-Sub output](complete-the-pids-for-dvb-sub.md) or [PIDs for SCTE\-27](complete-the-pids-for-scte27.md) or [PIDs for Teletext output](complete-the-pids-for-teletext.md)\.

1. You now have a captions encode that is fully defined\.

1. Repeat these steps to create captions in more outputs and output groups, as applicable\.
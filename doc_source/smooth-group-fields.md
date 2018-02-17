# Fields for Microsoft Smooth Group<a name="smooth-group-fields"></a>

## Microsoft Smooth Settings<a name="smooth-settings"></a>

+ Enter a name for the output group\. For example, **Sports Game 10122017 ABR** or **tvchannel59**\.

+ Choose **General configuration** if you want to change the default setup of the Microsoft Smooth manifest and fragments\. For details on a field, choose the Info link next to the field\.

+ Choose **Event configuration** if you want to change the configuration of the event information that is sent to the Microsoft IIS server\. For details on a field, choose the Info link next to the field\.

+ Choose **Timecode configuration** if you want to change the default setup of the timecode and timestamp that will be used in all the outputs in this output group\. For details on a field, choose the Info link next to the field\.

+ Choose **Sparse track** if you want all the outputs in this output group to include the SCTE\-35 messages that are already present in the input\. The messages will be included in a sparse track\. For details on a field, choose the Info link next to the field\. For details, see [[ERROR] BAD/MISSING LINK TEXT](scte-35-message-processing.md)\.

## Microsoft Smooth Destinations<a name="smooth-destinations"></a>

Specify the URLs for two destinations\. You must specify two destinations because AWS Elemental MediaLive works in redundant mode for outputs: it requires two destinations\. The URLs must use the HTTP or HTTPS protocol\. Do not include the port\. 

Specify the path portion of the destination as /folders/basefilename\. The basefilename will be used as the first part of the filename of all the files for all outputs in this output group\. Or specify it as /folders/\. In this case, the name of the input will be used for the filenames\. 

## Microsoft Smooth Outputs<a name="smooth-outputs"></a>

This section contains fields related to the encoding of the video, audio, and captions in the output, and related to the packaging and delivery of the output\. 

+ Choose **Add output** if you want more than one output in this output group\. An **Output** line is added for each output\. Setup of the individual outputs is described in [[ERROR] BAD/MISSING LINK TEXT](creating-a-channel-step5.md)\.

+ In the **Name modifier** field for each output, enter a modifier, if appropriate\. See examples for uses for this field\.
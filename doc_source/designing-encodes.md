# Step 4: Design the encodes<a name="designing-encodes"></a>

In the first step of planning the channel, you [identified](planning-encodes.md) the video, audio, and captions encodes to include in each output group\. In the third step, you organized these encodes into outputs in each output group\. 

You must now plan the configuration parameters for each encode\. As part of this plan, you identify opportunities for sharing encodes among outputs in the same output group in the channel, and among outputs in different output groups in the channel\.

**Result of this procedure**  
After you have performed this procedure, you will have a list of video, audio, and captions encodes to create\.

**Topics**
+ [Plan the encodes](#plan-encodes)
+ [Identify encode sharing opportunities](#plan-encode-sharing)

## Plan the encodes<a name="plan-encodes"></a>

In [Step 2: Map the output encodes to the sources](channel-map-output-source.md), you sketched out a plan for the encodes you want to create in each output group\. Below is the example of the plan from that step, showing the outputs and encodes, and the sources for those encodes\.

At some point, you must fill in the details for the encodes identified in the second and third columns of this table\. You have a choice:
+ You can decide these details now\. 
+ You can decide the details later, when you are actually creating the channel\. If you decide to do this, we recommend you still read the procedures after the table, to get an idea of what is involved in defining an encode\.


**Example**  
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/designing-encodes.html)

**Design the details for each video encode**

For each video encode in your table, you have already identified the source asset, codec, resolution and bitrate\. You must now identify all the other encoding parameters you need to set\.

Follow this procedure for each individual video encode\.

1. Look at the fields in the video encode section of each output\. To view these fields, follow these steps\. Don't worry about not completing all the sections\. You only want to display the video encode fields, and you will then cancel the channel\.
   + On the MediaLive home page, choose **Create channel**, and in the navigation pane, choose **Channels**\. 

     If you've created a channel before, you won't see the home page\. In that case, in the MediaLive navigation pane, choose **Channels**, and then choose **Create channel**\.
   + On the **Create channel** page, under **Output groups**, choose **Add**\. 

     Don't worry that you haven't completed any of the earliers sections in the channel\. You are only trying to display all the fields for the video encode\.
   + In the **Add output group** section, choose **HLS** and choose **Confirm**\.
   + Under that output group, choose **Output 1**\.
   + In the **Output** section, go to the **Stream settings** section, and choose the **Video** link\. 
   + In the **Codec settings** field, choose the codec that you want for this video encode\. More fields appear\. Choose the field labels for all the sections to display all the fields\.

1. In each section, determine whether you need to change the defaults\. 
   + Many of the fields have defaults, which means you can leave the field value as is\. For details about a field and its default value, choose the **Info** link next to the field\.
   + There are some fields that you might need to set according to instructions from your downstream system, to match the expectations of the downstream system\.
   + There are some fields where the value you enter affects the output charges for this channel\. These are:
     + The **Width** and **Height** fields \(which define the video resolution\)\.
     + The **Framerate** fields\.
     + The **Rate control** fields\.

     For information about charges, see [the MediaLive price list](https://aws.amazon.com/medialive/pricing/)\.
   + You can read about some of the fields in the following sections:
     + For information about the **Color space** fields, see [Color space handling in AWS Elemental MediaLive](color-space.md)\.
     + For information about the Additional encoding settings fields, see [Setting up enhanced VQ mode](video-enhancedvq.md)
     + For information about the **Rate control** fields, see [Setting the rate control mode](video-encode-ratecontrol.md)\. There are fields in this section that affect the output charges for this channel\. For more information about charges, see [the MediaLive price list](https://aws.amazon.com/medialive/pricing/)\.
     + For information about the **Timecode** fields, see [Timecode configuration](timecode.md)\.

1. Make detailed notes about the values for all the fields you plan to change\. Do this for every video encode that you identified\.

**Design the details for each audio encode**

For each audio encode in your table, you have already identified the source asset, codec and bitrate\. You must now identify all the other encoding parameters you need to set\.

Follow this procedure for each individual audio encode\.

1. Look at the fields in the audio encode section of each output\. To view these fields, follow the same steps as for the video encodes, but choose the **Audio 1** link\. 

   With audio encodes, there aren't many fields for each code\. But the fields for the codecs are very different from each other\.

1. Study the fields and make notes\. 

**Design the details for each captions encode**

For each captions encode in your table, you have already identified the source captions, format, and language\. You must now identify all the other encoding parameters you need to set\.

Follow this procedure for each individual captions encode\.

1. Look at the fields in the captions encode section of each output\. To view these fields, follow the same steps as for the video encodes, but choose Add caption to add a captions section, because there is no captions section by default\. 

   With captions encodes, there aren't many fields for each captions format\. But the fields for the formats are very different from each other\.

1. Study the fields and make notes\. 

## Identify encode sharing opportunities<a name="plan-encode-sharing"></a>

If you have already identified the details for all the output encodes, you can now identify opportunities for encode sharing\. 

If you plan to identify details later, we recommend that you come back to this section to identify opportunties\. 

Read about encode sharing and encode cloning in [Sharing encodes among outputs](feature-share-encode.md)\.

You will use encode sharing and encode cloning when you create the encodes in the channel, starting with [Step 6: Set up the video encode](creating-a-channel-step6.md)\.
+ When you have a complete list, compare the values for the encodes:
  + If you have two \(or more\) encodes with identical values, you can share the encode\. When you create the channel, you can create this encode once, in one output\. You can then reuse that encode in other outputs\. The procedure for creating the encode provides detailed instructions for reusing\.

    Keep in mind that two encodes are identical only if they are identical in all their fields, including sharing the same video source\. For example, in the sample table earlier in this section, the first video encode for HLS and the video encode for RTMP share the same video source\.
  + If you have two \(or more\) encodes with nearly identical values, you can clone an encode to create a second encode, and then change specific fields in the second encode\. The procedure for creating the encode provides detailed instructions for cloning\.

  Then identify opportunities for sharing, in the same way as you did for the video encodes\. Keep in mind that two encodes are identical only if they are identical in all their fields, including sharing the same audio source\. 

  Carefully identify the video encodes to share by noting the outputs and output groups each belongs to\.

Then identify opportunities for sharing, in the same way as you did for the video encodes\. Keep in mind that two encodes are identical only if they are identical in all their fields, including sharing the same captions source\. 

**Example**

Following from the example in the earlier steps in this section about channel planning, you might decide you have these opportunities shown in the last two columns of this table\.


****  

| Encode nickname |  Characteristics of the encode  | Source | Opportunity | Action | 
| --- | --- | --- | --- | --- | 
| VideoA |  AVC 1920x1080, 5 Mbps  | HEVC  |  | Create this encode from scratch\. | 
| VideoB |  AVC 1280x720, 3 Mbps  | HEVC  | Clone | Clone VideoA and change the bitrate\. Perhaps also other fields\. | 
| VideoC | AVC 320x240, 750 Kbps | HEVC  | Clone | Clone VideoA and change the bitrate and perhaps other fields\. | 
| AudioA | AAC 2\.0 in English at 192000 bps | AAC 2\.0 |  | Create this encode from scratch\. | 
| AudioB | AAC 2\.0 in French at 192000 bps | AAC 2\.0  | Clone | Clone AudioA and change the audio selector \(the reference to the source\) to the selector for French\. Perhaps also change other fields\. | 
| CaptionsA |  WebVTT \(object\-style\) converted from embedded, in English  | Embedded |  | Create this encode from scratch\. | 
| CaptionsB | WebVTT \(object\-style\) converted from embedded, in French | Embedded | Clone | Clone CaptionsC and change the captions selector \(the reference to the source\) to the selector for French\. Perhaps also change other fields\. | 
| VideoD | AVC 1920x1080, 5Mbps  | HEVC  | Share | Share VideoA | 
| AudioC | Dolby Digital 5\.1 in Spanish | Dolby Digital 5\.1  |  | Create this encode from scratch\. | 
| CaptionsC | RTMP CaptionInfo \(converted from embedded\) in Spanish | Embedded | Clone | Clone CaptionsA and change the captions selector \(the reference to the source\) to the selector for Spanish\. Perhaps also change other fields\. | 
| VideoE | AVC, 1920x1080, 5 Mbps | HEVC  | Share | Share VideoA | 
| AudioD | Dolby Digital 2\.0 in Spanish  | AAC 2\.0 |  | Create this encode from scratach\. Although its source is the same as Aa, its output codec is different, which means all its configuration fields are different\. Therefore, there is no advantage to cloning\. | 
| AudioE | Dolby Digital 2\.0 in French | AAC 2\.0  | Clone | Clone AudioD and change the audio selector \(the reference to the source\) to the selector for French\. Perhaps also change other fields\.Don't clone AuduioB because AudioB and AudioA have different output codecs\. Therefore, there is no advantage to cloning\. | 
| AudioF | Dolby Digital 2\.0 in English | AAC 2\.0 | Clone | Clone AuduioD and change the audio selector \(the reference to the source\) to the selector for English\. Perhaps also change other fields\.Don't clone AudioB because AudioB and AudioF have different output codecs\. Therefore, there is no advantage to cloning\. | 
| CaptionsD | DVB\-Sub \(object\-style\) converted from Teletext, in 6 languages\.  | Teletext |  | Create this encode from scratch\. | 
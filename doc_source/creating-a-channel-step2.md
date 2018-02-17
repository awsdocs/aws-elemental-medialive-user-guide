# Step 2: Set Up the Input<a name="creating-a-channel-step2"></a>

In this step, you select the input to attach to the channel and provide information about how to ingest the input\.

1. On the **Create channel **navigation pane, choose **Channel and input details**\. 

1. In the **Input specification** section, change the fields to match your input\. See below for details on the fields in this section\.

1. In the **Channel input** section, select an existing input\. More fields appear\. Complete the fields that apply to the selected input\. See below for details on specific fields\.

1. In the **Input settings** section, complete the fields as required\. For details on a field, choose the Info link next to the field\.

   + For most fields, the default values will work\. 

   + However, if you want to include audio and captions in the outputs, you must complete the **Audio selectors **and **Caption selectors** sections; the defaults do not specify enough information\.

1. When ready, go to the next step\.

**Input Specification Settings**

This section includes three fields that characterize the video in the input you intend to use with this channel\. The values in these fields are used to calculate the charges you will incur on the input side and to ensure that AWS Elemental MediaLive allocates sufficient processing resources, when you run this channel\. 

All the fields provide options that cover ranges, with the lowest range shown first and the highest shown last\. Lower ranges imply lower processing requirements, higher ranges imply higher requirements\.

For each field, make sure that you choose an option that meets or exceeds the requirements of your input\. If you do not, then AWS Elemental MediaLive may not allocate sufficient processing resources\. If you are not sure about the processing requirements of your input, choose a higher option\. For example, if you are not sure of the bitrate and you are trying to choose between 10 MBPS and 20 MBPS, then choose 20 MBPS, to be on the safe side\. Even with codecs, this advice applies: if you are not sure if your input is AVC \(H\.264\) or HEVC \(H\.265\), then choose HEVC\.

AWS Elemental MediaLive uses these values for billing and resource allocation purposes: you will pay for the option you specify\. For example, if you specify HD but the input is actually SD, you will be charged for HD\. 

But AWS Elemental MediaLive does not use these values for determining what is actually in the video for decoding purposes\. At ingest time, it still inspects the video to detect the source codec, resolution, and bitrate\. 

**Channel input \- RTP Push Input**

+ Look at the **Input destinations** section\. It shows the two locations on AWS Elemental MediaLive that the upstream system will push the source to, when the channel is running\. These locations were automatically generated when you created the input\. 

  For example, **rtp://198\.51\.100\.0:5000** and **rtp://198\.51\.100\.44:5000**\.

+ Choose **Input security group**; more information appears\. Make sure that an input security group is listed\.

  If a group is specified, you can continue\.

  If no group is specified, you cannot use this input because it has no input security group attached\. Typically, this situation occurs if, for example, you have input A attached to input security group B and then you delete B\. Input A is no longer useable\. You must recreate the input and attach an input security group to it before you can associate it with a channel you are creating\.

**Channel input \- RTMP Push Input**

+ Look at the **Input destinations** section\. It shows the two locations on AWS Elemental MediaLive that the upstream system will push the source to, when the channel is running\. These locations were automatically generated when you created the input\. Each location consists of an address portion that was automatically generated, appended by a folder you specified when you created the input\. 

  For example, **rtmp://198\.51\.100\.0:1935/movies/classic** and **rtmp://198\.51\.100\.45:1935/movies/classic**\.

+ Choose **Input security group**; more information appears\. Make sure that an input security group is listed\.

  If a group is specified, you can continue\.

  If no group is specified, you cannot use this input because it has no input security group attached\. Typically, this situation occurs if, for example, you have input A attached to input security group B and then you delete B\. Input A is no longer useable\. You must recreate the input and attach an input security group to it before you can associate it with a channel you are creating\.

**Channel input \- RTMP Pull Input**

Look at the **Input destinations** section\. It shows the locations of the source video; you specified these locations when you created the input\. 

For example, **rtmp://203\.0\.113\.0:1935/movies/classic** and **rtmp://203\.0\.113\.254:1935/movies/classic**\.

**Channel input \- HLS Pull Input **

Look at the **Input sources** section\. It shows the locations of the source video; you specified these locations when you created the input\. 

For example, **https://203\.0\.113\.0/newschannel/anytownusa\.m3u8** and **https://203\.0\.113\.254/newschannel/anytownusa\.m3u8** \(for an HTTPS pull\)\. 

Or **mediastoressl://eri39n\.data\.mediastore\.us\-west\-2\.amazonaws\.com/premium/canada/mlaw\.m3u8** and **mediastoressl://eri39n\.data\.mediastore\.us\-west\-2\.amazonaws\.com/redundant/premium/canada/mlaw\.m3u8** \(for an AWS Elemental MediaStore pull\)\. 

**Input Settings \- Network Input Settings**

Complete this section only if the input is HLS\. 

**Input Settings \- Other Settings**

The fields that are not within the **Network input settings** section apply to all inputs\. 

**Input Settings \- Video selector**

This section lets you identify the video to extract from the input, and lets you enable the optional color space feature\. 

+ In Video selector, choose Video selector\. More fields appear\. 

+ **Selector settings**: This field lets you identify the video to ingest\. 

  With RTP input, this field is optional but strongly recommended because the input may contain more than one video\. If you do not identify the video, AWS Elemental MediaLive selects the first video it finds, which may result in undesired content, especially in a live streaming context\. If you want to explicitly identify the video but do not know its program ID or PID, speak to the content provider\.

  With all other input types, this field is optional because the input only ever contains one video\.

  You can specify the video by specifying a program ID \(which typically exist in an MPTS input\) or by specifying a PID \(which exist in both MPTS and SPTS inputs\)\.

  Keep in mind that there is no button to add more video selectors because you can only extract one video asset from the input\.

+ **Color space** and **Color space usage**: These fields let you configure the optional color space feature\.

**Input Settings \- Audio selectors**

This section is required if you want to extract audio from the input\. You create one or more audio selectors to identify the audio to extract\. Typically, you identify different languages from the input, but you could also extract different audio codecs \(such as AAC and Dolby\)\.

For each audio you want to extract, choose **Add audio selector**\. Complete the fields that appear to identify the location of the audio and to specify optional handling of the audio\. 

**Input Settings \- Caption selectors**

This section is required if you want to extract captions from the input or to specify an external file as the source of the captions\. You create one or more captions selectors to identify the captions to extract\. Typically, you identify different languages in each selector, but you could also identify different captions formats\. 

For each caption item you want to extract or include, choose **Add captions **selector\. For detailed information on setting up input for captions, see [[ERROR] BAD/MISSING LINK TEXT](captions.md), specifically [[ERROR] BAD/MISSING LINK TEXT](#creating-a-channel-step2)\.
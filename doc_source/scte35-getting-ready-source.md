# Getting ready: Set the SCTE\-35 source—segments or manifest<a name="scte35-getting-ready-source"></a>

If you have HLS inputs in the channel, you must configure the input to identify the source of the SCTE\-35 messages\. There are two possible sources:
+ The segments in the transport stream \(TS\)\. This type of source applies to all inputs that can include SCTE\-35 messages\. Unless a specific SCTE\-35 packet identifier \(PID\) is selected, the first PID present in the TS will be used\.
+ Tags in an HLS input manifest\. This type of source applies only to HLS inputs\.

**To set the source in a non\-HLS input**

1. On the **Create/Edit channel** page, in the navigation pane, choose **Input attachments**\.

1. In **General input settings**, complete the following field:
   + **SCTE\-35 PID**: Enter the PID value\. If the value is left blank, the first SCTE\-35 PID present in the input will be selected\.

1. If appropriate, repeat for other **Input attachments**\.

**Note**  
You only need to follow this next procedure for HLS inputs\. For all other inputs, the source of the SCTE\-35 messages is always the TS segments\.

**To set the source in an HLS input**

1. On the **Create/Edit channel** page, in the navigation pane, choose **Input attachments**\. 

1. For each HLS input, in **Network input settings**, in **HLS input settings**, choose **HLS input**\. More fields appear\.

1. Set SCTE\-35 source to **SEGMENTS** \(the default\) or **MANIFEST**\.

**Topics**
+ [Supported manifest formats](#scte35-get-ready-source-support)
+ [How MediaLive creates the SCTE\-35 messages](#scte35-get-ready-source-create-message)
+ [How MediaLive inserts the message: preroll](#scte35-get-ready-source-preroll)

## Supported manifest formats<a name="scte35-get-ready-source-support"></a>

Read the following sections if you set up to use the HLS input manifest as the SCTE\-35 source\.

MediaLive can generate SCTE35 splice insert messages from **EXT\-X\-CUE\-OUT** and optionally **EXT\-X\-CUE\-IN** tags within the source HLS manifest\. Following are examples of supported formats for these tags\.
+ `#EXT-X-CUE-OUT:DURATION=60.000`
+ `#EXT-X-CUE-OUT:DURATION="60.000"`
+ `#EXT-X-CUE-OUT:60.000`
+ `#EXT-X-CUE-OUT:"60.000"`
+ `#EXT-X-CUE-IN`

## How MediaLive creates the SCTE\-35 messages<a name="scte35-get-ready-source-create-message"></a>

For each `EXT-X-CUE-OUT`, MediaLive creates an SCTE\-35 message of type splice insert with the following data:
+ `splice_event_id`: A number that increments, starting with 1 for the first CUE\-OUT message that MediaLive creates from the current input\. 
+ `out_of_network_indicator`: true \(1\)
+ `program_splice_flag`: true \(1\)
+ `duration_flag`: true \(1\)
+ `break_duration`:
  + `auto_return`: 1
  + `reserved`: 0
  + `duration`: The duration from the manifest, converted to 90kHz ticks\. For example, 15 seconds is 1350000 ticks\.
+ `splice_immediate_flag`: 0 \(false\)
+ `splice_time`: Use the video PTS of the first frame of the video segment that follows this EXT\-X\-CUE\-OUT in the input manifest
+ `unique_program_id`: 0
+ `avail_num`: A number that increments, starting with 1 for the first CUE\-OUT message that MediaLive creates from the current input\.
+ `avails expected`: 0

For each `EXT-X-CUE-IN`, MediaLive creates an SCTE\-35 message of type splice insert with the following data:
+ `splice_event_id`: The ID from the most recent EXT\-X\-CUE\-OUT in the manifest\.
+ `out_of_network_indicator`: false \(0\)
+ `program_splice_flag`: true \(1\)
+ `duration_flag`: false \(0\)
+ `splice_immediate_flag`: 0 \(false\)
+ `splice_time`: Use the video PTS of the first frame of the video segment that follows this EXT\-X\-CUE\-IN in the input manifest
+ `unique_program_id`: 0
+ `avail_num`: The value from the most recent EXT\-X\-CUE\-OUT
+ `avails expected`: 0

## How MediaLive inserts the message: preroll<a name="scte35-get-ready-source-preroll"></a>

MediaLive includes a preroll when it inserts the SCTE\-35 message that corresponds to the CUE\-OUT\. This preroll is 5 seconds in advance of the splice\_time in the SCTE\-35 message\. 

MediaLive reduces the preroll if the channel doesn't have enough buffering to allow the preroll\. The buffer, in seconds, is the product of the following:
+ Input segment duration, which is specified in the input manifest
+ Number of segments to include in the buffer\. You set this value in the **Buffer segments** field when you attach the HLS input\.

For example, if the segment duration is 6 seconds and the number of segments is 3, then the buffer is 18 seconds\.

**Ensuring an adequate preroll**

If the calculated buffer for your input is shorter than 5 seconds, MediaLive reduces the preroll\. MediaLive might reduce the preroll to 0, which would mean that the PTS value of the SCTE35 message equals the PTS of the splice time\.

To avoid an inadequate preroll, we recommend that you make sure that the buffer is *at least* equal to the preroll, plus one segment\. Follow these steps:
+ Step 1: Calculate the minimum buffer, in seconds, for your input: Preroll in seconds \+ length of one segment in seconds
+ Step 2: Calculate the number of segments in that minimum buffer: Divide the minimum buffer by the segment length
+ Step 3: Round that minimum up to a whole number\. Or that minimum is less than 3, round that number up to 3\.
+ Step 4: Enter this number \(or a bigger number, if you want\) in the **Buffer segments** in the Input attachment\. 

For example, assume the segment length is 2 sec\. 
+ Step 1: 5 \+ 2 = 7
+ Step 2: 7 secs divided by 2 = 3\.5
+ Step 3: Round up to 4\.
+ Step 4: Enter that number \(or a bigger number\) in the **Buffer segments** in the Input attachment\. 
# Captions in Channels with Multiple Inputs<a name="captions-channels-multi-input"></a>

 If your channel includes multiple inputs, these rules apply to the handling of captions: 
+ The captions formats in one input can be different from the captions formats in another input\. For example, you can have 608 embedded captions in one input and Teletext in another\. Or you can have DVB\-Sub in one input and no captions in another\. 
+ There is no requirement that all the inputs have captions that are capable of producing the specified captions in any given output\. 

  If the captions from an input cannot produce the specified captions in one of the outputs, the captions will be omitted for the duration of that input\. The channel will not fail\. When the channel switches to a different input, the captions will be included again if the captions from that input can produce the specified captions in that output\. 

**Example 1**  
You might have an RTP input as your primary live feed, and an MP4 as one of the other inputs\. The RTP input might have Teletext captions\. The MP4 input might have 608 embedded captions\. 
+ You might want to produce DVB\-Sub captions in a UDP output\. This is possible for both the input that has a Teletext source and the input that has a 608 embedded source\. 
+ You might want to produce Web\-VTT captions in an HLS output\. This is possible for both the input that has a Teletext source and the input that has a 608 embedded source\. 
+ You might want to produce 608 embedded captions in an Archive output\. This is not possible when the RTP input is active because Teletext captions can't be converted to 608 embedded captions\. For that period, there will be no captions included in the Archive output\. 

**Example 2**  
You might have an RTP input as your primary live feed, and an MP4 as one of the other inputs\. The RTP input might have Teletext captions\. The MP4 input might have DVB\-Sub captions\. 
+ You might want to produce Teletext captions in a UDP output\. This is possible when the RTP input is active, but it is not possible when the MP4 input is active because DVB\-Sub captions can't be converted to Teletext captions\. For that period, there will be no captions included in the UDP output\. 

**General Observations**  
The captions that are most restricted are the following: 
+ **ARIB in the input or output** – ARIB can only be passed through \(ARIB in, ARIB out\)\. 
+ **SCTE\-27 in the input** – It can be converted only to SMPTE\-TT\. However, it is not the only captions format that can be converted to SMPTE\-TT, so it might work for your workflow\. 
+ **Teletext in the output** – It can be produced only from Teletext input \(Teletext in, Teletext out\)\. 

 For the recommended procedure for setting up multiple inputs, see [Creating a Channel with Multiple Inputs](ips-create-channel-multi-inputs.md)\. 
# Sharing encodes among outputs<a name="feature-share-encode"></a>

You can share a single encode among several outputs within one channel\. You can clone an encode so that it serves as the basis for a new encode within the channel\.

## Sharing encodes<a name="encode-share"></a>

You can share an encode among several outputs when you want these outputs to have identical encodes\. When you share an encode, there is only one instance of the encode in the channel\. All the affected outputs use that encode\.

For example, you might have a channel containing these output groups:
+ One Archive output group, with one video encode\.
+ One HLS output group, with three video encodes in an ABR stack\.
+ One RTMP output group, with one video encode\.

The video encode in the RTMP output group might be identical to one of the video encodes in the HLS output group\. Therefore, instead of creating five video encodes, you would create four encodes\. You would set up the RTMP output group to share the appropriate encode from the HLS output group\.

Encode sharing applies to video, audio, and captions\. Sharing encodes reduces the effort of filling in fields\. It also reduces the risk of error when you intend to create identical encodes among outputs\. There is no chance that you will accidentally complete one field differently\.

These rules apply to encode sharing:
+ When you share an encode, you share all the fields, including the source selector for the encode\. 

  If you want to create two encodes that share all their configuration fields but are based on different sources, you *can't *share the single encode instance\. You should instead [clone the encode](#encode-clone)\.
+ You can share any encode among as many outputs as you want\.
+ You can share more than one encode in the channel\.
+ You can share only within the same channel\. You can't share across channels\.

For instructions to clone encodes when you are creating a channel, see [Step 6: Set up the video encode](creating-a-channel-step6.md), [Step 7: Set up the audio encodes](creating-a-channel-step7.md), and [Step 8: Set up the captions encodes](creating-a-channel-step8.md)\.

## Cloning encodes<a name="encode-clone"></a>

You can clone an encode so that it serves as the basis for a new encode within the channel\.

For example, you might have two audio encodes in the channel that share some fields\. You create the first audio encode\. You then create a second encode by cloning the first encode, and change any of the fields in the second encode\. In this case, the two encodes are separate instances\. 

These rules apply to encode sharing:
+ When you clone an encode, there are two instances of the encode, even if you don't change any fields in the second encode\.
+ After you have cloned the encode to create the new instance, you can change any of the fields, including the source selector for the encode\. 
+ You can combine sharing and cloning\. For example, you could clone encode A to create encode B\. You could then share encode B among two or more outputs\. 
+ You can clone more than one encode in the channel\.
+ You can clone only within the same channel\. You can't clone across channels\.

For instructions to clone encodes when you are creating a channel, see [Step 6: Set up the video encode](creating-a-channel-step6.md), [Step 7: Set up the audio encodes](creating-a-channel-step7.md), and [Step 8: Set up the captions encodes](creating-a-channel-step8.md)\.
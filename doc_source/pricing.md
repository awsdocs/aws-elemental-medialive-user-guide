# Pricing<a name="pricing"></a>

As with other AWS products, there are no contracts or minimum commitments for using AWS Elemental MediaLive\.

There are two components to pricing: pricing based on the input of the channel that is being processed, and pricing based on the outputs of the channel:
+ The input pricing is based on a combination of the input codec, the bitrate of the input, and the resolution of the input\. You specify these three characteristics in the input specification when you create the channel\. For more information, see [Input Specifications Settings](input-specification.md)\. 
+ The output pricing is based on a combination of the output codec, the output frame rate, and the output resolution\. You specify these values in the codec, frame rate, width, and height fields in the video settings of each output in the channel\. For more information, see [Step 7: Set Up the Video Encode](creating-a-channel-step6.md)\. Note that it is possible to set up the output frame rate to match the frame rate of the input\. In this case, the frame rate portion of the pricing calculation uses the rate for "30\-60 fps" frame rate; it doesn't use the actual input frame rate\.

There are different charges for inputs and outputs when the channel is running compared to when the channel is idle\.

As soon as you start a channel, running charges start accruing for inputs and outputs\. Running charges continue if you pause one or both pipelines in a channel\. Running charges stop accruing only when you stop the channel\.

For more information about pricing, see [https://aws.amazon.com/medialive/pricing/](https://aws.amazon.com/medialive/pricing/)\. 
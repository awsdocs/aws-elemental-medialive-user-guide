# Streams<a name="audio-only-streams-and-encodes"></a>

## Setting up encodes in streams<a name="audio-only-streams"></a>

Use the following settings for the streams in the output\.

**All outputs *except UDP***  
In the **Streams settings** section for each output, set up so that each output has one and only one audio encode\. Therefore you must do the following\.
+ Remove the video encode that MediaLive automatically adds\.
+ Make sure that you don't add any captions encodes\.

**UDP outputs**  
In the **Streams settings** section for the single output, set up so that each output contains only audio encodes\. Therefore you must do the following\.
+ Add as many audio encodes as you require\.
+ Remove the video encode that MediaLive automatically adds\.
+ Make sure that you don't add any captions encodes\.

## Configuring encodes<a name="audio-only-encodes"></a>

In the **Streams settings** section, in **Audio**, set up each encode as follows\.
+ In **Audio selector name**, choose one of the audio sources that you set up when you configured the input attachment\.
+ In **Codec settings**, choose any output audio codec that the output type supports\.
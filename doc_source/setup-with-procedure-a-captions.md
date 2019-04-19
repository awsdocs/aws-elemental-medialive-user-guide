# Setup with Embedded or Object\-style Captions<a name="setup-with-procedure-a-captions"></a>

This example shows how to implement [[the fourth use case](use-case-one-input-format-to-one-output-format-not-converted.md)](use-case-one-captions-output-multiple-video-encodes.md) from the typical scenarios\. For example, you want to produce an HLS output with three video encodes \(one for low\-resolution video, one for medium, one for high\) and one audio\. You also want to include embedded captions \(in English and Spanish\) and associate them with all three video encodes\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/captions_INembed_OUTembed_ABRhls_result.png)

**To set up for this use case**

1. In the channel that you are creating, in the navigation pane, in **Input attachments**, choose the input\. 

1. For **General input settings**, choose **Add captions selector** to create one captions selector\. Set **Selector settings** to **Embedded source**\.

1. Create an HLS output group\.

1. Create one output and set up the video and audio for low\-resolution video\.

1. In that same output, create one captions asset with the following:
   + **Captions selector name**: Captions selector 1\.
   + **Captions settings**: One of the Embedded formats\. 
   + **Language code** and **Language description**: Leave blank; with embedded passthrough captions, all the languages are included\.

1. Create a second output and set up the video and audio for medium\-resolution video\.

1. In that same output, create one captions asset with the following:
   + **Captions selector name**: Captions selector 1\.
   + **Captions settings**: One of the Embedded formats\. 
   + **Language code** and **Language description**: Keep blank\. With embedded captions, all the languages are included\.

1. Create a third output and set up the video and audio for high\-resolution video\.

1. In that same output, create one captions asset with the following:
   + **Captions selector name**: Captions selector 1\.
   + **Captions settings**: One of the Embedded formats\. 
   + **Language code** and **Language description**: Keep blank\. With embedded captions, all the languages are included\.

1. Finish setting up the channel and save it\. 
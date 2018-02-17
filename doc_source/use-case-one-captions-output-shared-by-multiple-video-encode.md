# Use Case: One Captions Output Shared by Multiple Video Encodes<a name="use-case-one-captions-output-shared-by-multiple-video-encode"></a>

This example shows how to set up captions in an ABR workflow\. The first setup shows how to set up an ABR workflow when the captions are in the same output as the video, meaning that the captions are either embedded or captions style\.

The second setup shows how to set up an ABR workflow when the captions belong to the sidecar category, in which case each captions is in its own output\.

## Setup with Embedded or Object\-style Captions<a name="setup-with-procedure-a-captions"></a>

This example shows how to implement the fourth use case from the typical scenarios\. For example, you want to produce an HLS output with three video encodes \(one for low\-resolution video, one for medium, one for high\) and one audio\. You also want to include embedded captions \(in English and Spanish\) and associate them with all three video encodes\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/captions_INembed_OUTembed_ABRhls_result.png)

1. In the channel that you are creating, in the navigation pane, choose **Channel and input details**\.

1. Choose **Add caption selector** to create one caption selector\. Set **Selector settings** to **Embedded source**\.

1. Create an HLS output group\.

1. Create one output and set up the video and audio for low\-resolution video\.

1. In that same output, create one captions asset with the following:

   + **Caption selector name**: Caption selector 1\.

   + **Caption settings**: One of the Embedded formats\. 

   + **Language code** and **Language description**: Leave blank; with embedded\-to\-embedded captions, all the languages are included\.

1. Create a second output and set up the video and audio for medium\-resolution video\.

1. In that same output, create one captions asset with the following:

   + **Caption selector name**: Caption selector 1\.

   + **Caption settings**: One of the Embedded formats\. 

   + **Language code** and **Language description**: Leave blank; with embedded captions, all the languages are included\.

1. Create a third output and set up the video and audio for high\-resolution video\.

1. In that same output, create one captions asset with the following:

   + **Caption selector name**: Caption selector 1\.

   + **Caption settings**: One of the Embedded formats\. 

   + **Language code** and **Language description**: Leave blank; with embedded captions, all the languages are included\.

1. Finish setting up the channel and save it\. 

## Setup with Sidecar Captions<a name="setup-with-procedure-b-captions"></a>

This example shows an ABR workflow where the captions are in sidecars\. For example, you want to produce a Microsoft Smooth output with three video encodes \(one for low\-resolution video, one for medium, one for high\) and one audio\. These encodes are in a Microsoft Smooth output\. You want to ingest embedded captions \(in English and Spanish\) and convert them to TTML captions, one for English and one for Spanish\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/captions_INembed_OUTembed_ABRmss_result.png)

1. In the channel that you are creating, in the navigation pane, choose **Channel and input details**\.

1. Choose **Add caption selector** twice to create the following caption selectors:

   + Caption selector 1: for Embedded English\.

   + Caption Selector 2: for Embedded Spanish\.

1. Create a Microsoft Smooth output group\.

1. Create one output that contains one video encode and set it up for low\-resolution video\.

1. Create a second output that contains one video encode and set it up for medium\-resolution video\.

1. Create a third output that contains one video encode and set it up for high\-resolution video\.

1. Create a fourth output that contains one audio encode and no video encode\.

1. Create a fifth output that contains one captions encode and no video or audio encodes, and with the following settings for the captions encode:

   + **Caption selector name**: Caption selector 1\.

   + **Caption settings**: TTML\. 

   + **Language code** and **Language description**: English\.

1. Create a sixth output that contains one captions encode and no video or audio encodes, and with the following settings for the captions encode:

   + **Caption selector name**: Caption selector 2\.

   + **Caption settings**: TTML\. 

   + **Language code** and **Language description**: Spanish\.

1. Finish setting up the channel and save it\. 
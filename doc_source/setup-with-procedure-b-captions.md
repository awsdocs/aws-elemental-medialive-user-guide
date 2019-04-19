# Setup with Sidecar Captions<a name="setup-with-procedure-b-captions"></a>

This example shows an ABR workflow where the captions are in sidecars\. For example, you want to produce a Microsoft Smooth output with three video encodes \(one for low\-resolution video, one for medium, one for high\) and one audio\. These encodes are in a Microsoft Smooth output\. You want to ingest embedded captions \(in English and Spanish\) and convert them to TTML captions, one for English and one for Spanish\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/captions_INembed_OUTembed_ABRmss_result.png)

**To set up for this use case**

1. In the channel that you are creating, in the navigation pane, for **Input attachments**, choose the input\. 

1. For **General input settings**, choose **Add captions selector** twice to create the following captions selectors:
   + Captions selector 1: for Embedded English\.
   + Captions Selector 2: for Embedded Spanish\.

1. Create a Microsoft Smooth output group\.

1. Create one output that contains one video encode and set it up for low\-resolution video\.

1. Create a second output that contains one video encode and set it up for medium\-resolution video\.

1. Create a third output that contains one video encode and set it up for high\-resolution video\.

1. Create a fourth output that contains one audio encode and no video encode\.

1. Create a fifth output that contains one captions encode and no video or audio encodes, and with the following settings for the captions encode:
   + **Captions selector name**: Captions selector 1\.
   + **Captions settings**: TTML\. 
   + **Language code** and **Language description**: English\.

1. Create a sixth output that contains one captions encode and no video or audio encodes, and with the following settings for the captions encode:
   + **Captions selector name**: Captions selector 2\.
   + **Captions settings**: TTML\. 
   + **Language code** and **Language description**: Spanish\.

1. Finish setting up the channel and save it\. 
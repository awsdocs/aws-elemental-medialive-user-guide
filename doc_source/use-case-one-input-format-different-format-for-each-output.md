# Use Case C: One Input Format Converted to Different Formats, One Format for Each Output<a name="use-case-one-input-format-different-format-for-each-output"></a>

This example shows how to implement [[the third use case](use-case-one-input-format-to-one-output-format-not-converted.md)](use-case-one-input-format-to-several-output-formats.md) from the typical scenarios\. The input is set up with one format of captions and two or more languages\. You want to produce several different types of output\. In each output, you want to convert the captions to a different format but include all the languages\.

For example, the input has Teletext captions in Czech and Polish\. Assume that you want to produce a Microsoft Smooth output and an HLS output\. Assume that in the Microsoft Smooth output, you want to include one video and one audio and you want to convert the captions to TTML\. In the HLS output, you want to include one video and one audio and you want to convert the captions to Web\-VTT\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/captions_INttext_OUT_OPmss_hls_result.png)

**To set up for this use case**

1. In the channel that you are creating, in the navigation pane, for **Input attachments**, choose the input\. 

1. For **General input settings**, choose **Add captions selector** twice to create the following captions selectors:
   + Captions selector 1 for Teletext Czech\. Specify the page that holds the Czech captions\.
   + Captions selector 2 for Teletext Polish\. Specify the page that holds the Polish captions\.

   Although you are including the captions in two different outputs \(Microsoft Smooth and HLS\), you need to extract them from the input only once, so you need to create only one captions selector for each language\.

1. Create a Microsoft Smooth output group and configure it as follows: 
   + Create one output and set up the video and audio\. 
   + Create a second output that contains one captions encode and no video or audio encodes, and with the following settings: 
     + **Captions selector name**: Captions Selector 1\.
     + **Captions settings**: TTML\. 
     + **Language code** and **Language description**: Czech\.
     + **Style control**: Set as desired\.
   + Create a third output that contains one captions encode and no video or audio encodes, with the following settings:
     + **Captions selector name**: Captions Selector 2\.
     + **Captions settings**: TTML\.
     + **Language code** and **Language description**: Polish\.
     + Other fields: same as the second output \(the Czech captions\)\.

1. Create an HLS output group and configure it as follows: 
   + Create one output and set up the video and audio\. 
   + Create a second output that contains one captions encode and no video or audio encodes, and with the following settings: 
     + **Captions selector name**: Captions Selector 1\.
     + **Captions settings**: Web\-VTT\. 
     + **Language code** and **Language description**: Czech\.
     + Other fields: Set as desired\.
   + Create a third captions output that contains one captions encode and no video or audio encodes, and with the following settings:
     + **Captions selector name**: Captions Selector 2\.
     + **Captions settings**: Web\-VTT
     + **Language code** and **Language description**: Polish\.
     + Other fields: same as the second output \(the Czech captions\)\.

1. Finish setting up the channel and save it\.
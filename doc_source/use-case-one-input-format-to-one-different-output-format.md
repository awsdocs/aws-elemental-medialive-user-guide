# Use Case B: One Input Format Converted to One Different Output Format<a name="use-case-one-input-format-to-one-different-output-format"></a>

This example shows how to implement [[the second use case](use-case-one-input-format-to-one-output-format-not-converted.md)](use-case-one-input-format-to-different-output-formats.md) from the typical scenarios\. The input includes two captions languages, and the single output converts those captions\. For example, the input has embedded captions in German and French\. You want to produce a UDP output with both captions converted to DVB\-Sub, plus one video and one audio\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/captions_INembed_OUTdvb_udp_result.png)

**To set up for this use case**

1. In the channel that you are creating, in the navigation pane, for **Input attachments**, choose the input\. 

1. For **General input settings**, choose **Add captions selector** twice, to create Captions selector 1 \(for German\) and Captions selector 2 \(for French\)\. In both cases, set **Selector settings** to **Embedded source**\.

1. Create a UDP output group\. 

1. Create one output and set up the video and audio\.

1. In this output, choose **Add captions** to create a captions encode\. 
   + **Captions selector name**: Captions selector 1\. 
   + **Captions settings**: DVB\-Sub\. 
   + **Language code** and **Language description**: German\.
   + Other fields: Keep the defaults or complete as desired\. 

1. Choose **Add captions** again to create another captions encode\. Set up this encode for the French captions\. Make sure that you set up the font fields for German and French in exactly the same way\. 

1. Finish setting up the channel and save it\.
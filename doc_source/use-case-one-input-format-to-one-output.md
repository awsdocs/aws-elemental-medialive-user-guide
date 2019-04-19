# Use Case A: One Input Format to One Output and Not Converted<a name="use-case-one-input-format-to-one-output"></a>

This example shows how to implement [the first use case](use-case-one-input-format-to-one-output-format-not-converted.md) from the typical scenarios\. The input is set up with one format of captions and two or more languages\. Assume that you want to maintain the format in the output, and that you want to produce only one type of output and include all the languages in that output\.

For example, the input has embedded captions in English and French\. You want to produce an HLS output that includes embedded captions in both English and French, plus one video and one audio\.

This example illustrates two important features of an embedded passthrough workflow\. First, you don't create separate captions selectors; all the languages are automatically included\. Second, if you are outputting to HLS, there is an opportunity to specify the languages and the order in which they appear\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/captions_INembed_OUTembed_hls_result.png)

**To set up for this use case**

1. In the channel that you are creating, in the navigation pane, for **Input attachments**, choose the input\.

1. For **General input settings**, choose **Add captions selector** to create one captions selector\. Set **Selector settings** to **Embedded source**\.

1. Create an HLS output group\.

1. Create one output and set up the video and audio\. 

1. In that same output, create one captions asset with the following:
   + **Captions selector name**: Captions selector 1\.
   + **Captions settings**: One of the Embedded formats\. 
   + **Language code** and **Language description**: Keep the field blank\. With embedded captions, all the languages are included\.

1. In the HLS output group, in **Captions**, for **Captions language setting**, choose **Insert**\. 

1. For **HLS settings**, in **Captions language mappings**, choose **Add captions language mappings** twice \(once for each language\)\.

1. Complete the first group of mapping fields with **1**, **ENG**, and **English** and the second group with **2**, **FRE**, and **French**\.

1. Finish setting up the channel and save it\.
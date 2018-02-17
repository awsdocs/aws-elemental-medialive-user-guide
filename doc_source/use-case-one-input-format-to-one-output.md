# Use Case: One Input Format to One Output<a name="use-case-one-input-format-to-one-output"></a>

This example shows how to implement the first use case from the typical scenarios\. The input is set up with one format of captions and two or more languages\. You want to maintain the format in the output\. You want to produce only one type of output and include all the languages in that output\.

For example, the input has embedded captions in English and French\. You want to produce an HLS output that includes embedded captions in both English and French, plus one video and one audio\.

This example illustrates two important features of an embedded\-to\-embedded workflow\. First, you do not create separate caption selectors; all of the languages are all automatically included\. Second, if you are outputting to HLS, there is an opportunity to specify the languages and the order in which they appear\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/captions_INembed_OUTembed_hls_result.png)

## Setup<a name="procedure2"></a>

1. In the channel that you are creating, in the navigation pane, choose **Channel and input details**\.

1. For **Input settings**, choose **Add caption selector** to create one caption selector\. Set **Selector settings** to **Embedded source**\.

1. Create an HLS output group\.

1. Create one output and set up the video and audio\. 

1. In that same output, create one captions asset with the following:

   + **Caption selector name**: Caption selector 1\.

   + **Caption settings**: One of the Embedded formats\. 

   + **Language code** and **Language description**: Leave blank; with embedded captions, all the languages are included\.

1. In the HLS output group, in **Captions**, in **Caption language setting**, choose **Insert**\. 

1. For **HLS settings**, in **Caption language mappings**, choose **Add caption language mappings** twice \(once for each language\)\.

1. Complete the first group of mapping fields with "1," "ENG," and "English" and the second group with "2," "FRE," and "French\."

1. Finish setting up the channel and save it\.
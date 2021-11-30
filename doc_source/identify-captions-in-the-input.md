# Step 1: Create captions selectors in the input<a name="identify-captions-in-the-input"></a>

You must identify the captions that you want to use and assign each to a captions selector\. If you don't create any captions selectors, you can't include captions in the output\. All the captions will be removed from the media\.

Then you must extract the captions that you want by adding a captions selector in the channel\. Each extracted captions asset is contained in one captions selector\. For example, one selector contains the Teletext captions in Czech\.

**To identify the captions that you want**

1. Identify which captions are in the input \(the provider of the input should provide you with this information\)\. Identify the captions formats and, for each format, the languages\. 

1. Identify which of those formats and languages that you want to use\.

   If you are converting DVB\-Sub or SCTE\-27 captions to WebVTT, see [Constraints for outputs that use OCR conversion](captions-supported-features.md#captions-languages-ocr) for limits on the number of languages that MediaLive can ingest\.

1. Determine how many captions selectors to create in the input in the channel\. Follow this guidance: 
+ **ARIB passthrough** – Create a single captions selector for all languages \(in fact, one captions selector for the entire content\)\. All languages are passed through; there is no other option\. 
+ **Embedded passthrough** – Create a single captions selector for all languages\. All languages are passed through; there is no other option\. For details, see [Information for embedded ](embedded.md)\.
+ **Embedded In, Other Out** – Specify the language to extract from the input and the language to include in an output\. The specified language is extracted from the embedded captions and converted to the new format\.
+ **DVB\-Sub or SCTE\-27 In, WebVTT** – Create one caption selector for each language, to a maximum of three caption selectors in the input\. For more information about this limit, see [Constraints for outputs that use OCR conversion](captions-supported-features.md#captions-languages-ocr)\.
+ **Teletext passthrough** – Create a single captions selector for all languages \(in fact, one captions selector for the entire content\)\. All languages are passed through; there is no other option\. For details, see [Information for Teletext](teletext.md)\.
+ **Teletext conversion** – If you have Teletext source and want a different format in the output, create one captions selector for each language and format combination\.
+ **Any Other Combination** – Create one captions selector for each language and format combination\.

You end up with a list of captions selectors to create\. For example:
+ Captions Selector 1: Teletext captions in Czech
+ Captions Selector 2: Teletext captions in Polish

**To create a captions selector**

1. In the channel that you are creating, in the navigation pane, in **Input attachments**, choose the input\. 

1. For **General input settings**, choose **Add captions selectors**\.

1. For **Captions selector name**, enter a suitable name\. For example, **Teletext Czech**\. 

1. For **Selector settings**, choose the format of the source captions\. 

1. For most formats, more fields appear\. For details about a field, choose the Info link next to the field\. In addition, see [DVB\-Sub or SCTE\-27](dvb-sub-or-scte27.md), [Embedded](embedded.md), or [Teletext](teletext.md)\.

1. Create more captions selectors, as required\. 
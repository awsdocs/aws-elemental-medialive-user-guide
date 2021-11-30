# Support for multiple languages<a name="support-for-languages"></a>

If the source includes captions in multiple languages, you can include multiple languages in the output as follows:
+ **Embedded passthrough** – For any of the embedded source formats, if you specify embedded as the output format, all languages that are in the input are included in the output\. You can't remove any of the languages\.
+ **Embedded In, Other Out** – For any of the embedded source formats, if you are setting up for “embedded in, other out,” you can specify which languages to extract and include in an output\.
+ **Teletext passthrough** – If you have Teletext source and want Teletext in the output, then all languages \(pages\) are included in the output\. You can't strip out any languages\. In fact, the entire Teletext content is included in the output; you can't strip out any of the pages\. Furthermore, Teletext passthrough is supported only in TS outputs\.
+ **Teletext conversion** – If you have Teletext source and want a different format in the output, you can specify the language to extract from the input and the language to include in an output\.
+ **ARIB passthrough** – For an ARIB source, the only possible output is ARIB\. All the languages that are in the input are included in the output\. You can't strip out any languages\. 
+ **Any Other Combination** – For all other sources, you always specify the language to extract from the input and the language to include in an output, regardless of the source format and output format\.
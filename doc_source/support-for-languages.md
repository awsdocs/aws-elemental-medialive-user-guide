# Support for Languages<a name="support-for-languages"></a>

If the source includes captions in multiple languages, you can include multiple languages in the output as follows:

+ **Embedded\-to\-Embedded**\. For any of the embedded source formats, if you are doing “embedded in, embedded out” \(also known as embedded\-to\-embedded\), all languages that are in the input are included in the output\. You can't remove any of the languages\.

+ **Embedded In, Other Out**\. For any of the embedded source formats, if you are doing “embedded in, other out,” you can specify which languages to extract and include in an output\.

+ **Teletext\-to\-Teletext**\. For teletext source, if you are doing “teletext in, teletext out” \(also known as teletext\-to\-teletext\), all languages \(pages\) are included in the output\. You can't strip out any languages\. In fact, the entire teletext content is included in the output; you can't strip out any of the pages\. Furthermore, teletext\-to\-teletext is supported only in TS outputs\.

+ **Teletext In, Other Out**\. For teletext source, if you are doing “teletext in, other out,” you can specify which languages to extract and which languages to include in an output\.

+ **Any Other Combination**\. For all other sources, you always specify the language to extract from the input and the language to include in an output, regardless of the source format and output format\.
# Supported features<a name="captions-supported-features"></a>

This section provides information on the different features of captions that AWS Elemental MediaLive supports\.

**Topics**
+ [Supported formats](supported-formats.md)
+ [Format support by output container](supported-format-outputs.md)
+ [Constraints for outputs that use OCR conversion](#captions-languages-ocr)
+ [Support for multiple languages](support-for-languages.md)
+ [Support for font styles in output captions](support-for-font-styles-in-output-captions.md)

## Constraints for outputs that use OCR conversion<a name="captions-languages-ocr"></a>

MediaLive uses OCR \(optical character recognition\) technology for the following scenarios:
+ The input captions are DVB\-Sub or SCTE\-27
+ The output captions are WebVTT format

**Constraint in supported languages**

OCR conversion uses language libraries\. Language libraries are a critical component of conversion\. They speed up conversion because the tool can check character strings against a dictionary, instead of recognizing words letter by letter\. You must specify the language of a captions source so that MediaLive can choose the correct library\. If you choose a language that doesn’t match the language of the captions, conversion accuracy will be poor\. 

MediaLive currently includes libraries for six languages, which means that MediaLive can perform an OCR conversion only with the following source languages:
+ Dutch
+ English
+ French
+ German
+ Portuguese
+ Spanish

**Constraint in number of languages in one input**

OCR conversion uses more processing resources than other captions conversions\. Therefore, in each input, you can create a maximum of three captions selectors that will use OCR conversion\. 

These rules apply:
+ A selector uses OCR conversion if the specified format is DVB\-Sub or SCTE\-27, and at least one output encode that uses the selector is a [WebVTT encode](output-sidecar-and-smptett-mss.md)\. 
+ A DVB\-Sub or SCTE\-27 selector doesn't use OCR conversion \(and doesn't count towards the limit\) if, for example, the selector is used only in SMPTE\-TT encodes\.
+ If the selector is used in more than one WebVTT encode \(for example, in two output groups\), the selector counts only once towards the limit\.
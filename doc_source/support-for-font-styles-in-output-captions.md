# Support for font styles in output captions<a name="support-for-font-styles-in-output-captions"></a>

Depending on the scenario, there are three possibilities for the font style for output captions:
+ You can specify the style that you want for fonts, including color, outline, and background color\.
+ The font styles in the input are passed through\.
+ The font styles are controlled by the downstream player\.

The procedures later in this chapter describe how to set up font styles\. You might set up the styling of the output captions on the [input side](identify-captions-in-the-input.md), on the [output side](captions-outputs-details-specific-formats.md), or on both sides\.


**Font style options**  

|  Source captions  |  Output captions  |  Options for font style  | 
| --- | --- | --- | 
|  ARIB  |  ARIB  |  None\. The font styles in the input are automatically passed through in the output\.  | 
|  Any supported captions format  |  Burn\-in  |  You can specify font styles in the output\. If you don’t specify styles, the AWS Elemental MediaLive defaults are used\.   | 
|  DVB\-Sub  |  DVB\-Sub  |  None\. The font styles in the input are automatically passed through in the output\.  | 
|  Any supported captions format  |  DVB\-Sub  |  You can specify font styles in the output\. If you don’t specify styles, the AWS Elemental MediaLive defaults are used\.   | 
| An Embedded Combination \(Embedded, Embedded\+SCTE\-20, SCTE\-20\+Embedded\) | EBU\-TT\-D | You can specify some of the style information and take some of the information from the input captions\. Or you can set up the captions with no style data\. | 
| Teletext | EBU\-TT\-D | You can specify some of the style information and take some of the information from the input captions\. Or you can set up the captions with no style data\. | 
|  Teletext  |  Teletext  |  None\. The font styles in the input are automatically passed through in the output\.  | 
|  An Embedded Combination \(Embedded, Embedded\+SCTE\-20, SCTE\-20\+Embedded\)  |  TTML  |  You can set up to copy the font information from the source to the output\.   | 
|  Teletext  |  TTML  |  You can set up to copy the font information from the source to the output\.  | 
|  An Embedded Combination \(Embedded, Embedded\+SCTE\-20, SCTE\-20\+Embedded\)  |  WebVTT  |  You can set up to pass through color and position style information from the source to the output\. Or you can set up the captions with no style data\.  | 
|  Teletext  |  WebVTT  |  You can set up to pass through color and position style information from the source to the output\. Or you can set up the captions with no style data\.  | 
|  Any Other  |  Any Other  |  No control: the font style is always determined by the downstream player\.   | 
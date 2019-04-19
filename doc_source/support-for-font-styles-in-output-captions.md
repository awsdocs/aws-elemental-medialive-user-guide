# Support for Font Styles in Output Captions<a name="support-for-font-styles-in-output-captions"></a>

Depending on the scenario, there are three possibilities for the font style for output captions:
+ You can specify the style that you want for fonts, including color, outline, and background color\.
+ The font styles in the input are passed through\.
+ The font styles are controlled by the downstream player\.


**Font Style Options**  

|  Source Captions  |  Output Captions  |  Options for Font Style  | 
| --- | --- | --- | 
|  ARIB  |  ARIB  |  None\. The font styles in the input are automatically passed through in the output\.  | 
|  Any supported captions format  |  Burn\-in  |  You can specify font styles in the output\. If you don’t specify styles, the AWS Elemental MediaLive defaults are used\.   | 
|  DVB\-Sub  |  DVB\-Sub  |  None\. The font styles in the input are automatically passed through in the output\.  | 
|  Any supported captions format  |  DVB\-Sub  |  You can specify font styles in the output\. If you don’t specify styles, the AWS Elemental MediaLive defaults are used\.   | 
| SCTE\-27 | SCTE\-27 | None\. The font styles in the input are automatically passed through in the output\. | 
|  Teletext  |  Teletext  |  None\. The font styles in the input are automatically passed through in the output\.  | 
|  An Embedded Combination \(Embedded, Embedded\+SCTE\-20, SCTE\-20\+Embedded\)  |  TTML  |  The font information in the source can be copied to the output, or you can let the downstream player determine the font style\.   | 
|  Teletext  |  TTML  |  The font information in the source can be copied to the output, or you can let the downstream player determine the font style\.  | 
|  Any Other  |  Any Other  |  No control: the font style is always determined by the downstream player\.   | 
# Support for Font Styles in Output Captions<a name="support-for-font-styles-in-output-captions"></a>

Depending on the scenario, you can specify the style for fonts, including color, outline, and background color\.


**Font Style Options**  

|  Source Caption  |  Output Caption  |  Options for Font Style  | 
| --- | --- | --- | 
|  ARIB  |  ARIB  |  None\. The font styles in the input are automatically passed through in the output\.  | 
| SCTE\-27 | SCTE\-27 | None\. The font styles in the input are automatically passed through in the output\. | 
|  DVB\-Sub  |  DVB\-Sub  |  None\. The font styles in the input are automatically passed through in the output\.  | 
|  Teletext  |  Teletext  |  None\. The font styles in the input are automatically passed through in the output\.  | 
|  Any Supported Caption  |  Burn\-in  |  You can specify font styles in the output\. If you don’t specify styles, the AWS Elemental MediaLive defaults are used\.   | 
|  Any Supported Caption  |  DVB\-Sub  |  You can specify font styles in the output\. If you don’t specify styles, the AWS Elemental MediaLive defaults are used\.   | 
|  An Embedded Combination \(Embedded, Embedded\+SCTE\-20, SCTE\-20\+Embedded\)  |  TTML  |  The font information in the source can be copied to the output, or you can let the downstream player determine the font style\.   | 
|  Teletext  |  TTML  |  The font information in the source can be copied to the output, or you can let the downstream player determine the font style\.  | 
|  Any Other  |  Any Other  |  No control: the font style is always determined by the downstream player\.   | 
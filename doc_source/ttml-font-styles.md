# Font styles for TTML<a name="ttml-font-styles"></a>

If the source captions are embedded or Teletext captions, and the output captions are TTML, you can optionally specify some of the font style information\. 

**To specify font information**

1. In the output that has the TTML captions, display the section for the captions\. 

1. Set **Style control** to **Passthrough** or **Use\_configured**\.

   Note that when **User\_configured** is selected, there are actually no fields that you can configure\.

The XML file for the captions includes the following style information:


| Style information | Value in XML file for Passthrough option | Value in XML file for User\-configured option | 
| --- | --- | --- | 
| Font style information \(position, alignment, italics, and so on\) | Set to match the source captions\. | Left blank\. | 
| Font color and background color | Set to match the source captions\. | Set to white font and black background\. | 
| Font size  | Match size of source captions, if specified\. Otherwise, set to 80% of the available height available for captions\. | Left blank\. | 
| Font family | Match family of source captions, if specified\. Otherwise, set to monospaceSansSerif\. | Left blank\. | 
| Line gap  | Set to leave the line gap unfilled\. | Set to leave the gap unfilled\. | 
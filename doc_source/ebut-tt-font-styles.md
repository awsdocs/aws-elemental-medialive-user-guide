# Font styles for EBU\-TT\-D<a name="ebut-tt-font-styles"></a>

If the source captions are embedded or Teletext captions, and the output captions are EBU\-TT\-D, you can optionally specify some of the font style information\. 

An EBU\-TT\-D caption encode consists of an XML file that the downstream system reads and processes\. This XML file includes a section for font style information\. You can specify some of this information\.

**To specify font information**

1. In the output that has the EBU\-TT\-D captions, display the section for the captions\.

1. Complete these fields\. For details about a field on the MediaLive console, choose the **Info** link next to the field\.
   + **Style control**
   + **Fill line gap**
   + **Font family**

This setup results in one of the following options:

The XML file for the captions includes the following style information:


| Style information | Value in XML file for Include option | Value in XML file for Exclude option | 
| --- | --- | --- | 
| Font style information \(position, alignment, italics, and so on\) | Set to match the source captions\. | Left blank\. | 
| Font color and background color | Set to match the source captions\. | Set to white font and black background\. | 
| Font size  | Set to 100%\. | Set to 100%\. | 
| Font family | Set to the value that you specified in Font family\. | Set to monospaced\. | 
| Line gap  | Set up to match the value that you specified in Fill line gap\.  | Set up to leave the gap unfilled\. | 
# Font styles for WebVTT<a name="webvtt-font-styles"></a>

If the source captions are embedded or Teletext captions, and the output captions are WebVTT, you can optionally pass through some of the style information\.

**No\_Style\_Data** is selected by default\. This value outputs only text and timestamp information on the caption encode\. 

If **Passthrough** is selected, position and color style data will be passed through to the output\. This also includes the text and timestamp information\. 

**To specify style information**

1. In the output that has the WebVTT captions, display the section for the captions\. 

1. Set **Style control** to **No\_Style\_Data** or **Passthrough**\.

   Note that when either is selected, there are no fields that you can configure\. On **Passthrough**, position and color style data will be passed through to the output\. On **No\_Style\_Data**, only the text and timestamp information will be passed through\.
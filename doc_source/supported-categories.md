# Supported Captions Categories<a name="supported-categories"></a>

Different formats are grouped into the same category\. For example, TTML and WebVTT are grouped in the "sidecar" category\. AWS Elemental MediaLive supports several categories of captions\. The main ones are the following:

+ Embedded\. The captions are carried inside the video encode\. 

+ Captions Object\. The captions are in their own "captions encode\." They are not part of the video encode\. But they are in the same output as their corresponding video and audio encodes\. 

+ Sidecar\. The captions are each in their own output, separate from the output that contains the video and audio\. There can be several "captions\-only" outputs, for example, one for each desired language\. 

You need to be aware of captions categories when you set up captions in the output\. For more information about all categories and which category each captions format belongs to, see [[ERROR] BAD/MISSING LINK TEXT](categories-captions.md)\.
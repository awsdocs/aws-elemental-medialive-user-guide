# General information about color space<a name="about-color-metadata"></a>

Following is some general information about color space\.

## Definitions<a name="color-space-definitions"></a>

The source video might use a specific *color space* and a specific *brightness function*\. The source video might also carry *metadata *that describes aspects of the color\.
+ The color space specifies a range of pixel colors that can apply to the content\. 

  MediaLive supports two SDR color spaces and two HDR color spaces\. For more information about the scope of the support, see [How MediaLive supports the color space standards](#colorspace-support)\.
+ The brightness function controls the brightness of each pixel\. The brightness is also known as gamma tables, lookup tables \(LUT\), electro\-optical transfer function \(EOTF\), and transfer function\. 
+ There are three possible sets of metadata:
  + Color space metadata, which specifies which color space applies to the content\. The content is said to be marked for a color space\. 
  + Brightness function metadata, which specifies which brightness function applies to the content\. 
  + Display metadata\. 

## Color space standards<a name="color-space-standards"></a>

Each color space has different standards for the three sets of color data\. 

To read this table, find a color space in the first column, then read across to identify the three sets of color data for that color space\.


****  

|  MediaLive term for the color space   |  Complies with this color space standard   |  Complies with this brightness function standard   |  Complies with this standard for display metadata   | 
| --- | --- | --- | --- | 
|  601 or rec601   |  SDR rec\. 601   |  BT\.1886   |  Not applicable\. This color space doesn't include display metadata\.  | 
|  709 or rec709   |  SDR rec\. 709   |  BT\.1886   |  Not applicable\. This color space doesn't include display metadata\.  | 
|  HDR10   |  rec\.2020  |  SMPTE ST 2084 \(PQ\)   |  SMPTE ST 2086   | 
|  HLG or HLG 2020   |  rec\.2020  |  HLG rec\. 2020   | Not applicable\. This color space doesn't include display metadata\. | 

Note that HDR10 and HLG use the same color space\. They use different brightness functions and display metadata standards\.

## How MediaLive supports the color space standards<a name="colorspace-support"></a>

On the input side, MediaLive can read the metadata for all four color space standards\. On the output side, MediaLive can produce the color space \(including the metadata\) for three of the color space standards\. 


****  

|  Color space   |  MediaLive can read the information in the input?   |  MediaLive can produce the color space in the output  | 
| --- | --- | --- | 
|  601  |  Yes  |  Yes  | 
|  709   |  Yes  |  Yes  | 
|  HDR10   |  Yes  |  Yes  | 
|  HLG  |  Yes  | No | 

MediaLive can't read the information in the input that comes from an AWS Elemental Link device\. But when you set up the input, you can specify the color space that applies\.
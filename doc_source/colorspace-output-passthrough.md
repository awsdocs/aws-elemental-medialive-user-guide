# Passing through color space<a name="colorspace-output-passthrough"></a>

To pass through all existing color space metadata, in **Codec details**, expand **Color space** and set **Color space settings** to **Color space passthrough**\. The following table shows how MediaLive handles each type of color space that it encounters\.


|  Color space metadata that MediaLive encounters  |  How MediaLive handles the color space  | 
| --- | --- | 
|  Content in any color space that MediaLive supports  |  Doesn't touch the color space or brightness \(the pixel values\) in the output\. Passes through any of the three sets of metadata that are present\.  | 
| Content marked with unknown or an unsupported color space |  Doesn't touch the color space or brightness \(the pixel values\) in the output\. Leaves the content as marked with the unknown color space\.  Passes through any brightness metadata and display metadata\.  | 
|  Content with no color space metadata  |  Doesn't touch the color space or brightness \(the pixel values\) in the output\. Leaves the content as unmarked \(no color space metadata\)\.  | 
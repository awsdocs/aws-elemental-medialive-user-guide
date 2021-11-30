# Removing color space metadata<a name="colorspace-output-remove"></a>

To remove all color space metadata, in **Codec details**, expand **Color space** and set **Color space settings** to **Don't include**\. The following table shows how MediaLive handles each type of color space it encounters\.


|  Color space metadata that MediaLive encounters  |  How MediaLive handles the color space  | 
| --- | --- | 
|  Content in any color space that MediaLive supports Content with no color space metadata Content with unknown or unsupported color space metadata  | MediaLive does the following for all content:[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/colorspace-output-remove.html)The output won't contain any color space metadata, brightness metadata, or display metadata\. | 
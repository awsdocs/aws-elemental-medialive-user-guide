# Information for Teletext<a name="teletext"></a>

Teletext is a form of data that can contain several types of information, not just captions\. Teletext can be handled in one of the following ways:
+ If you want to include the entire Teletext input, you must set up for Teletext passthrough\. The entire Teletext can never be converted to another format\. 
+ Individual captions pages \(the captions in a specific language\) can be extracted and converted to another captions format\.
+ Individual captions pages \(the captions in a specific language\) *cannot* be extracted and kept in Teletext\. If you want to extract individual captions pages, you must convert them to another format\.

**How many captions selectors?**
+ If you are setting up for Teletext passthrough captions, create only one captions selector, even if you want to include multiple languages in the output\. With this scenario, all languages are automatically extracted and included in the output\. 
+ If you are setting up for Teletext\-to\-other, create one captions selector for each language that you want to include in the output\. For example, one selector to extract English Teletext, and one selector to extract Swedish Teletext\.
+ If you are setting up for Teletext passthrough in some outputs and Teletext\-to\-other in other outputs, create one captions selector for each language that you want to include in the output\. Don't worry about a selector for the passthrough output\. MediaLive passes through all the data, even though there isn't a selector to explicitly specify this action\. 

**Captions selector fields**
+ **Selector settings** – Choose **Teletext**\.
+ **Page number** – This field specifies the page of the desired language\. Complete as follows: 
  + If you are setting up for Teletext passthrough captions \(you are creating only one captions selector for the input captions\), keep the field blank\. The value is ignored\.
  + If you are converting Teletext to another format \(you are creating several captions selectors, one for each language\), complete the **Language code** field to specify the page for the language that you want\. If you leave this field blank, you get a validation error when you save the channel\. 

**Including a positioning rectangle**

If you plan to convert the source captions to EBU\-TT\-D, you can optionally define a rectangle that positions the captions on the video frame in the output\. If you choose to use this feature, it will apply as follows:
+ It will apply to all your EBU\-TT\-D outputs that use this captions selector\. 
+ It won't apply to any other formats of output captions that use this caption selector\. The positioning information is simply omitted from these other captions formats\.

You define the rectangle relative to the underlying video frame\. For example, you specify the position of the left edge of the rectangle as a percentage of the entire width of the video frame\. A value of 10 means "calculate a value X that is 10% of the frame width\. Then find the left edge of the video frame and move X pixels into the frame and draw the left edge of the rectangle"\.

Specifying a percentage, rather than a fixed number, means that the rectangle works for different video renditions \(different resolutions\) in the same output\.

**To define a positioning rectangle**

1. In the **Output rectangle** field, choose **Caption rectangle**\.

1. Complete the fields for the four sides of the rectangle – **Left offset**, **Width**, **Top offset**, and **Height**\.
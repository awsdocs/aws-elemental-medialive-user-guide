# Information for Teletext<a name="teletext"></a>

Teletext is a form of data that can contain several types of information, not just captions\. Teletext can be present in TS input, in which case it might be referred to as “DVB Teletext\.” Teletext can be handled in one of the following ways:

+ If you want to include the entire teletext input, you must do teletext\-to\-teletext\. The entire teletext can never be converted to another format\. Teletext\-to\-teletext is supported only in a TS output\. 

+ Individual captions pages \(the captions in a specific language\) can be extracted and converted to another captions format\.

+ Individual captions pages \(the captions in a specific language\) *cannot* be extracted and kept in teletext\. If you want to extract individual captions pages, you must convert them to another format\.

**How Many Caption Selectors?**

+ If you are doing teletext\-to\-teletext captions, create only one caption selector, even if you want to include multiple languages in the output\. With this scenario, all languages are automatically extracted and are automatically included in the output\. 

+ If you are doing teletext\-to\-other, create one caption selector for each language that you want to include in the output\. For example, one selector to extract English teletext, and one selector to extract Swedish teletext\.

+ If you are doing teletext\-to\-teletext in some outputs and teletext\-to\-other in other outputs, create one caption selector for the teletext\-to\-teletext, and then create individual selectors for the teletext\-to\-other, one for each language being converted\.

**Caption Selector Fields**

+ **Selector settings**: Choose **Teletext**\.

+ **Page number**: This field specifies the page of the desired language\. Complete as follows: 

  + If you are doing teletext\-to\-teletext captions \(you are creating only one caption selector for the input captions\), leave blank: the value is ignored\.

  + If you are converting teletext to another format \(you are creating several caption selectors, one for each language\), specify the page for the desired language\. If you leave this field blank, you will get a validation error when you save the channel\. 
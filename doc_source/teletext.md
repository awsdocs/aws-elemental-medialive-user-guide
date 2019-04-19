# Information for Teletext<a name="teletext"></a>

Teletext is a form of data that can contain several types of information, not just captions\. Teletext can be handled in one of the following ways:
+ If you want to include the entire Teletext input, you must set up for Teletext passthrough\. The entire Teletext can never be converted to another format\. Teletext passthrough is supported only in a TS output\. 
+ Individual captions pages \(the captions in a specific language\) can be extracted and converted to another captions format\.
+ Individual captions pages \(the captions in a specific language\) *cannot* be extracted and kept in Teletext\. If you want to extract individual captions pages, you must convert them to another format\.

**How Many Captions Selectors?**
+ If you are setting up for Teletext passthrough captions, create only one captions selector, even if you want to include multiple languages in the output\. With this scenario, all languages are automatically extracted and are automatically included in the output\. 
+ If you are setting up for Teletext\-to\-other, create one captions selector for each language that you want to include in the output\. For example, one selector to extract English Teletext, and one selector to extract Swedish Teletext\.
+ If you are setting up for Teletext passthrough in some outputs and Teletext\-to\-other in other outputs, create one captions selector for each language that you want to include in the output\. Don't worry about a selector for the passthrough output\. MediaLive passes through all the data, even though there is not a selector to explicitly specify this action\. 

**Captions Selector Fields**
+ **Selector settings** – Choose **Teletext**\.
+ **Page number** – This field specifies the page of the desired language\. Complete as follows: 
  + If you are setting up for Teletext passthrough captions \(you are creating only one captions selector for the input captions\), keep the field blank\. The value is ignored\.
  + If you are converting Teletext to another format \(you are creating several captions selectors, one for each language\), specify the page for the language that you want\. If you leave this field blank, you get a validation error when you save the channel\. 
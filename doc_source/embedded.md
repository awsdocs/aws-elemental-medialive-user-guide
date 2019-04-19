# Information for Embedded<a name="embedded"></a>

Read this section if the input captions are any of the following: embedded \(EIA\-608 or CEA\-708\), embedded\+SCTE\-20, SCTE\-20\+embedded, or SCTE\-20\.

**How Many Captions Selectors?**
+ If you are setting up for embedded passthrough, create only one captions selector\. With this scenario, all languages are automatically extracted and are automatically included in the output\.
+ If you are setting up for embedded\-to\-other, create one captions selector for each language that you want to include in the output, to a maximum of four selectors\.
+ If you are setting up for embedded passthrough in some outputs and embedded\-to\-other in other outputs, create one captions selector for each language that you want to include in the output, to a maximum of four selectors\. Don't worry about a selector for the embedded passthrough output\. MediaLive extracts all the languages for that output, even though there is not a selector to explicitly specify this action\. 

**Captions Selector Fields**
+ **Selector settings**: 
  + Choose embedded if the source captions are embedded \(EIA\-608 or CEA\-708\), embedded\+SCTE\-20, or SCTE\-20\+embedded\.
  + Choose SCTE\-20 if the source captions are SCTE\-20 alone\.
+ **EIA\-608 track number** – This field specifies the language to extract\. Complete as follows: 
  + If you are setting up for embedded passthrough only \(you are creating only one captions selector for the input embedded captions\), this field is ignored, so keep the default\.
  + If you are converting embedded to another format \(you are creating several captions selectors, one for each language\), specify the number of the CC instance \(from the input\) that holds the language that you want\.
+ **Convert 608 to 708**: The embedded source captions can be EIA\-608 captions, CEA\-708 captions, or both EIA\-608 and CEA\-708\. You can specify how you want these captions to be handled when AWS Elemental MediaLive is ingesting content\. The following table describes the behavior for various scenarios\.    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/embedded.html)
+ **SCTE\-20 detection** – If the source captions combine embedded \(EIA\-608 or CEA\-708\) and SCTE\-20, you might want to set this field to **Auto**\. AWS Elemental MediaLive gives preference to the 608/708 embedded captions but switches to use the SCTE\-20 captions when necessary\. If you set this field to **Off**, AWS Elemental MediaLive never uses the SCTE\-20 captions\.
# Identify the captions encodes<a name="channel-planning-captions-encodes"></a>

You must decide on the number of captions encodes\. Follow this procedure for each output group\. 

1. Determine the maximum number of captions encodes that are allowed in the output group\. The following rules apply for each type of output group\.  
****    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/channel-planning-captions-encodes.html)

1. Identify the category each caption format belongs to\. See the list in [Captions categories](categories-captions.md)\. For example, WebVTT captions are sidecar captions\.

1. Use this category to identify the number of captions encodes you need in the output group\.
   + For embedded captions, you always create one captions encode\.
   + For object\-style captions and sidecar captions, you create one captions encode for each format and language that you want to include\.
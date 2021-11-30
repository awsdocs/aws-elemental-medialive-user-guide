# Assess the captions in the sources<a name="ips-assess-captions"></a>

 There are special requirements for the captions in sources for a multiple\-input channel\. 

**To assess the captions in the sources**

1. Read each of the requirements that follow for information on specific constraints in the captions sources\. Make sure that the captions in each source meets these requirements\.

1. If you reject a source, you might want to contact the upstream system to determine if it could provide a more suitable version of the source content\. 

## First requirement: a source must contain all required captions languages and formats<a name="ips-captions-req-1"></a>

With a multiple\-input channel, for every output there must be a captions asset in the source that can produce the captions in that output\. If a source doesn't have all the source captions to produce all the output captions, it can't be used as a source in a multiple\-input channel\.

For example, assume that the channel contains an Archive output group that contains one output with one captions encode for embedded captions in English, French, Spanish, and German\. The channel also contains one HLS output group that contains four captions outputs, one each for English, French, Spanish, and German Web VTT captions\.

Every source must include a captions source that can produce both embedded and Web VTT captions\. The source can contain one captions source that can produce both output types, or the source can contain two captions sources:
+ Assume that you have a source that contains embedded captions in the four languages\.

  This source is acceptable because embedded captions can produce embedded captions in the output and Web VTT captions in the output\.
+ Assume that you have a source that contains DVB Sub in the four languages\.

  This source is *not* acceptable because DVB Sub captions can't produce embedded captions in the output\.
+ Assume that you have a source that contains embedded captions in English, French, German, and Bulgarian\.

  This source is *not* acceptable because one of the languages is Bulgarian instead of Spanish\.
+ Assume that you have a source that contains embedded captions in English and French\.

  This source is *not* acceptable because it is missing two of the output languages\.

## Second requirement: for embedded passthrough all sources must contain languages in the same order<a name="ips-captions-req-2"></a>

When there is at least one output that has embedded captions and there are at least two sources that have embedded captions, the languages must be in the same order in those sources\. 

*Passthrough *means that an output requires embedded captions encodes in one or more languages, and a source contains embedded captions \(typically in four languages\)\. For example, the output requires English and Spanish embedded captions\. A source contains embedded captions in English and Spanish, and possibly in two other languages\. 

If two sources have the embedded captions languages in a different order, you can't use both the sources in the multiple\-input channel\. You must use only one of the sources\. 

Look again at the example from the preceding requirement:
+ Assume that you have a source that contains embedded captions with the languages in the four channels in this order: English, French, Spanish, and German\. 

  Assume that you have a second source that contains embedded captions with the languages in a different order: French, Spanish, German, and English\. 

  Only one of these sources is acceptable\. 

When this scenario applies to your channel, you should decide which sources to keep and which ones to reject\. One rule you could follow is the following: 
+ Compare the order of the captions languages in those sources\.
+ Identify the order of the most important source, or identify the order that most sources follow\.
+ Accept only the sources that follow this order\. Reject the other sources\.

**Note**  
This requirement applies only to embedded passthrough\.  
If the channel doesn't contain any outputs that contain embedded captions, then you can use any source that contains embedded captions because the order of the languages in the sources isn't relevant\. The embedded captions aren't passed through\. They are converted to another format, such as DVB\-Sub\. 
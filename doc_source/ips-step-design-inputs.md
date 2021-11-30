# Step 3: Organize sources into static and dynamic inputs<a name="ips-step-design-inputs"></a>

This section is a supplement to the information in [Working with inputs in AWS Elemental MediaLive](creating-input.md)\. It provides information that applies to inputs used in a multiple\-input channel\. 

After you follow step 2 to assess the sources, you end up with a set of sources that are suitable for your multiple\-input channel\. You must now organize these sources into three types of MediaLive inputs: static live inputs, static file inputs, and dynamic file inputs\.

**Result of this step**

After this step, you have a list of the following:
+ Sources that you will set up as static live inputs\. Each source becomes one input \(and one input attachment\)\.
+ Sources that you will set up as static file inputs\. Each source becomes one input \(and one input attachment\)\.
+ Sources that you will set up as dynamic files inputs\. Several sources become one input \(and one input attachment\)\.

## Identify the live sources<a name="ips-identify-live"></a>

Make a note of the sources that are live sources\. Each of these sources becomes a static live input\.

## Identify and organize file sources<a name="ips-organize-file-sources"></a>

You must assess your files sources and determine if you should implement some sources as dynamic inputs, rather than as static inputs\.

A static input is always associated with the same source\. A dynamic input can be associated with a different source each time that you attach it to the channel\. It is therefore more flexible and can help you work with the limit on the number of inputs attached to a channel\. For general information about dynamic inputs, see [Static inputs and dynamic inputs](how-dynamic-inputs-work.md)\.

**To organize the sources**

1. Organize the file sources into sets, where the sources in each set are all stored in the same source location with the same access credentials, such as the same bucket in Amazon S3\. 

   For example, you might have a set of file sources in the bucket called "prerolls," and another set in the bucket called "filler"\. Each bucket has different access credentials, so each one is its own set\.

1. Read this step if you have inputs with embedded captions that you are converting \(instead of passing through\)\. If you don't have inputs with embedded captions, or if you do have inputs with embedded captions but they are always passed through to the output, then skip this step\.
   + Within each set, identify the file sources that contain embedded captions\. Determine if there is at least one output that is converting these captions rather than passing them through\.
   + In each file source that contains embedded captions, identify the order of the languages\.
   + Where necessary, subdivide the set according to language order\.

     For example, you might have one set of file sources in an Amazon S3 bucket where the languages are in the order English, French, Spanish, and German\. You might have another set in the same bucket where the order is French, Spanish, German, and English\. Divide this set into two sets\.

1. Make a list of the sets that you identified\. For example, you might have these sets: 
   + File sources from the Amazon S3 "preroll" bucket with embedded captions in the order English, French, Spanish, and German
   + File sources from the Amazon S3 "filler" bucket with embedded captions in the order French, Spanish, German, and English
   + File sources from the Amazon S3 "filler" bucket with embedded captions in a different order, such as English, French, Spanish, and German

1. Decide whether each set of file sources becomes a static file input or a dynamic file input\. Follow these rules:
   + Any set that contains more than one file source becomes one dynamic input\. 
   + Any set that contains only one file source can become a static input\. However, if you think you might later use other file sources from that location \(for example, from that Amazon S3 bucket\), you might want to treat the set as a dynamic input, in order to not exceed the [limit for file inputs](eml-limitations-and-rules.md#limits-inputs)\.
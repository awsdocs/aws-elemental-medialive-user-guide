# Step 2: Map the output encodes to the sources<a name="channel-map-output-source"></a>

In the first step of planning the channel, you identified the number of encodes you need in each output group\. You must now determine which assets from the source you can use to produce those encodes\.

**Result of this procedure**  
After you have performed this procedure, you will have identified the following key components that you will create in the channel:
+ The video input selectors 
+ The audio input selectors
+ The captions input selectors

Identifying these components is the last step in planning the *input* side of the channel\. 

**To map the output to the sources**

1. Obtain the *list of output encodes* you want to produce\. You created this list in the [previous step](planning-encodes.md)\. It is useful to organize this list into a table\. For example:  
**Example**    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/channel-map-output-source.html)

1. Obtain the *list of sources* that you created when you assessed the source content and collected identifiers\. For an example of such a list, see [Result of this step](assess-uss-result.md)\.

1. In your table of output encodes, add two more columns, labeled *Source* and *Identifier in source*\. 

1. For each encode \(column 2\), find a line in the *list of sources* that can produce that encode\. Add the source codec and the identifier of that source codec\. This example shows a completed table\.  
**Example**    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/channel-map-output-source.html)

   You will use this information when you create the channel:
   + You will use the source and source identifier information when you [create the input selectors](input-video-selector.md)\.
   + You will use the characteristics information when you [create the encodes](creating-a-channel-step6.md) in the output groups\.

1. After you have identified the source assets, group those assets that are being used more than once, to remove the duplicates\.

1. Label each asset by its type—video, audio, or captions\.  
**Example**    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/channel-map-output-source.html)

## Example of mapping<a name="channel-map-example"></a>

The following diagrams illustrate the mapping of the output encodes back to source assets\. The first diagram shows the outputs \(at the top\) and the sources \(at the bottom\)\. The other three diagrams shows the same outputs and sources with the mappings for video, for audio, and for captions\.

**Encodes and assets**

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/channel-design-map-in-out.png)

**Mapping video encodes to assets**

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/channel-design-map-in-out-V.png)

**Mapping audio encodes to assets**

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/channel-design-map-in-out-A.png)

**Mapping captions encodes to assets**

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/channel-design-map-in-out-C.png)
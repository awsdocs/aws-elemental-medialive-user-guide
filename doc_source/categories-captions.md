# Step 3: Match Formats to Categories<a name="categories-captions"></a>

There are different procedures to follow to create captions encodes in the output\. The correct procedure depends on the "category" that the output captions belong to\. There are five categories of captions, described after the table\. 

On the list of outputs that you have created, make a note of the category that each captions option belongs to\. 


|  Captions Format  |  Category of This Format  | 
| --- | --- | 
|  ARIB   |  Object  | 
|  Burn\-in  |  Burn\-in  | 
|  DVB\-Sub  |  Object  | 
|  Embedded  |  Embedded  | 
|  Embedded\+SCTE\-20  |  Embedded   | 
|  RTMP CaptionInfo  |  Object  | 
|  SCTE\-20\+Embedded  |  Embedded  | 
| SCTE\-27 | Object | 
| SMPTE\-TT | Stream in Microsoft Smooth | 
|  Teletext   |  Object  | 
|  TTML  |  Sidecar  | 
|  Web\-VTT  |  Sidecar  | 

For example, your list of outputs might now look like this: 
+ Microsoft Smooth output with TTML captions \(sidecar\) in Czech
+ Microsoft Smooth output with TTML captions \(sidecar\) in Polish
+ HLS output with Web\-VTT captions \(sidecar\) in Czech
+ HLS output with Web\-VTT captions \(sidecar\) in Polish

## Embedded in Video<a name="embedded-in-video"></a>

The captions are carried inside the video encode, which is itself in an output in the output group\. There is only ever one captions asset within that video encode, although that asset might contain captions for several languages\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/caption_categories_embedded.png)

## Captions Object<a name="captions-object"></a>

All the captions encodes for a given output group are in the same output as the corresponding video and audio\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/caption_categories_object.png)

## Sidecar<a name="captions-sidecar"></a>

Each captions encode for a given output group is in its own "captions\-only" output\. The output group can contain more than one captions output, for example, one for each language\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/caption_categories_sidecar.png)

Each captions\-only output becomes a separate file in the packaged output\.

## Stream<a name="captions-stream"></a>

Each captions encode for a given output group is in its own "captions\-only" output\. The output group can contain more than one captions output, for example, one for each language\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/caption_categories_stream.png)

Each captions\-only output becomes a separate stream in the packaged output\.

## Burn\-in<a name="burnin"></a>

The captions are converted into text and then overlaid on the picture directly in the video encode\. Strictly speaking, once the overlay occurs, these are not really captions because they are indistinguishable from the video\. 
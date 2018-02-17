# Step 3: Match Formats to Categories<a name="categories-captions"></a>

There are different procedures to follow to create caption encodes in the output\. The correct procedure depends on the "category" that of the output captions belongs to \. There are five categories of captions, described in the following table\.

On the list of outputs that you have created, make a note of the category that each captions option belongs to\. 


|  Captions Format  |  Category of This Format  | 
| --- | --- | 
|  ARIB   |  Object  | 
|  Burn\-in  |  Burn\-in  | 
|  DVB\-Sub  |  Object  | 
|  Embedded  |  Embedded  | 
|  Embedded\+SCTE\-20  |  Embedded   | 
|  SCTE\-20\+Embedded  |  Embedded  | 
| SCTE\-27 | Object | 
| SMPTE\-TT | Stream in Microsoft Smooth | 
|  Teletext   |  Object  | 
|  TTML  |  Sidecar  | 
|  WebVTT  |  Sidecar  | 

For example, your list of outputs might now look like this: 

+ Microsoft Smooth output with TTML captions \(sidecar\) in Czech\.

+ Microsoft Smooth output with TTML captions \(sidecar\) in Polish\.

+ HLS output with Web\-VTT captions \(sidecar\) in Czech\.

+ HLS output with Web\-VTT captions \(sidecar\) in Polish\.

## Embedded in Video<a name="embedded-in-video"></a>

The captions are carried inside the video encode, which is itself in an output in the output group\. There is only ever one captions asset within that video encode, although that asset might contain captions for several languages\. 

## Captions Object<a name="captions-object"></a>

The captions are in their own "captions encode" in an output in the output group\. They are not part of the video encode\. However, they are in the same output as their corresponding video and audio encodes\. There might be several captions encodes in the output, for example, for different languages\. 

## Sidecar<a name="sidecar"></a>

The captions are each in their own output in the output group, separate from the output that contains the video and audio\. Each captions output contains only one captions asset \(file\)\. The output group might contain several "captions\-only" outputs, for example, one for each language in the output group\.

## SMPTE\-TT in Microsoft Smooth<a name="stream-in-mss"></a>

The captions are handled as a separate stream in Microsoft Smooth\. 

## Burn\-in<a name="burnin"></a>

The captions are converted into text and then overlaid on the picture directly in the video encode\. Strictly speaking, once the overlay occurs, these are not really captions because they are indistinguishable from the video\. 
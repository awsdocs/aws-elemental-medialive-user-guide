# Categories for inputs<a name="input-categories"></a>

Inputs can be categorized in several ways:
+ **Type** – An input has a type of source and delivery protocol\. For example, an HLS input or an RTMP input\. For more information, see [Reference: Supported input containers and codecs](inputs-supported-containers.md)\.
+ **Live versus VOD ** – An input is either a live \(streaming\) input or a video on demand \(VOD\) input\. For more information, see [Reference: Supported input containers and codecs](inputs-supported-containers.md)\.
+ **Push versus pull** – An input is either a push input or a pull input\.
  + With a push input, the upstream system pushes the input to *endpoints* on MediaLive\. The input holds these endpoints\.
  + With a pull input, MediaLive pulls the input from the upstream system\. The input holds these *source* addresses on the upstream system\. 

  For more information, see [Reference: Supported input containers and codecs](inputs-supported-containers.md)\.
+ **Input class** – An input can be set up as either a standard\-class input or single\-class input:
  + You can use a standard\-class input with a standard channel or a single\-pipeline channel\. 
  + You can use a single\-class input only with a single\-pipeline channel\. 

  For more information on the purpose of input classes, see [Implementing pipeline redundancy](plan-redundancy-mode.md)\.

  For information on the classes applicable to each input type, see [Supported input class](inputs-single-standard-vpc.md)\.
+ **Static versus dynamic** – When you create the input, you decide if it is static or dynamic\.
  + A static input has a URL \(that points to the content source\) that never changes\. 

    Any input type can be set up as a static input\.
  + A dynamic input has a URL that includes a variable portion\. It is intended for use with input switching\. 

    Only MP4 and Transport Stream \(TS\) inputs can be set up as dynamic inputs\.

  For more information, see [Input switching in AWS Elemental MediaLive](scheduled-input-switching.md)\.
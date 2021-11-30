# Step 1: Verifying the input<a name="pipeline-locking-verify-input"></a>

You must speak to your upstream system to make sure that the input source meets these requirements:
+ The type of input\. The input *cannot *be HLS\.
+ Whether the input has embedded timecode\. These rules apply:
  + For both [locking modes](pipeline-locking-set-up.md#pipeline-locking-mode), the input must have an embedded timecode\.
  + For epoch\-locking mode, the embedded timecode must be within 2 minutes of epoch time\. If the timecode is off by more than 2 minutes, MediaLive considers that the source doesn't meet the requirements for pipeline locking\.
+ If the source has varying framerates, each input framerate must be a simple conversion to the desired output framerate\. For information about simple conversions, see the requirements later in this section\.

If the input doesn't meet these requirements, you can still use it, but there is no point in following the rest of these procedures because MediaLive won't perform pipeline locking in any of the outputs\. This means that there is no guarantee that the two pipelines will be frame\-accurate with each other\. 

**Frame rate requirements**

The conversion between the input frame and the desired output framerate must be *simple*, which means that one of these statements must apply:
+ The output framerate must be a whole number multiple of the input framerate\. For example, the input framerate might be 45 FPS, and the output framerate might be 90 FPS\.
+ The input framerate must be a whole number multiple of the output framerate\. For example, the input framerate might be 60 FPS, and the output framerate might be 30 FPS\.

Note that with these rules, it is possible for the framerates to be integers\. For example, if the input framerate is 29\.97 FPS and the output framerate is 59\.94 FPS\.

Following are examples of *complex* framerates\. You can't use the input if one of these combinations apply to your channel:
+ Input FPS is 59\.4, output FPS is 60\.
+ Input FPS is 45, output FPS is 60\.
+ Input FPS is 29\.97 FPS, output FPS is 23\.978\.
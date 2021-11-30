# Troubleshooting<a name="pipeline-locking-tshoot"></a>

Pipeline locking ensures that the two pipelines in a standard channel are frame accurate with each other, in the output groups where MediaLive performs pipeline locking\.

If you or the downstream system notice that the pipelines are not synchronized, perform the following troubleshooting:
+ Make sure that MediaLive supports pipeline locking for the type of input in your channel\.
+ Make sure that the input source has an embedded timecode\.
+ If you chose epoch\-locking mode, make sure that the embedded timecode is within 2 minutes of epoch time\.
+ Make sure that MediaLive supports pipeline locking in the output group that is not synchronized\.
+ Make sure that you changed the **Framerate control** so that it's not **Initialize\_from\_source**\.
+ Make sure that the input framerate and output framerate are a simple conversion of each other\.
+ If the framerate within the source changes, it's possible that MediaLive can't perform pipeline locking for the duration because for that section of video, there is no simple framerate conversion\.
+ Make sure that you remembered to set up segmentation markers in a UDP output group\. For the other supported output groups, you don't need to worry about this because their outputs are always segmented\.
+ Make sure that you set up the segmentation marker type that your downstream system expects\.
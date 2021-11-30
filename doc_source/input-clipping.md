# Input clipping<a name="input-clipping"></a>

You can clip a file input so that MediaLive ingests only a portion of the file\. The file must be an MP4 file that is stored on Amazon S3, AWS Elemental MediaStore, or an HTTP server that supports HTTP range requests\.

You clip a file as part of setting up an input switching action in the channel schedule\. Therefore, to use a clipped file, you must use the schedule\. 

The integration with input switching works as follows\. When MediaLive is getting ready to switch to the file input that includes input clipping, MediaLive sends a request to the upstream system, to request a portion of the file, rather than the entire file\.

**To set up a file input for input clipping**

1. If the upstream system is an HTTP server, confirm with that system that they support range requests\. If the server doesn't support range requests, there will be an input loss problem when the input switch occurs\.

1. Create the MP4 file input in the usual way\. See [Creating an MP4 pull input](mp4-pull-input.md)\.

1. Attach the input to the channel in the usual way\. See [Step 2: Attach inputs to the channel](creating-a-channel-step2.md)\. 

1. Create a switch input action in the schedule that specifies the start time and end time for the clip\. See [Creating actions in the schedule \(console\)](schedule-using-console-create.md)\.

   You can specify a start point \(if you don't specify one, the ingest starts at the beginning of the file\)\. You can specify an endpoint \(if you don't specify one, the ingest stops at the end of the file\)\. Or you can specify both a start point and end point\.

When the channel switches to this input, it starts and stops ingesting the file at the specified points\.

You can reuse this same input repeatedly, each time specifying a different portion to ingest\. To do so, create another switch input action, with different start and end times\. 
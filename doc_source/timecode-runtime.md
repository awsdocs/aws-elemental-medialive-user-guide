# How timecode works at runtime<a name="timecode-runtime"></a>

**Initial channel start**

When you start the channel, MediaLive samples the input timecode \(if you set up the source as embedded\)\. After that, MediaLive generates a timecode for each output frame that it produces, incrementing the timecode with each frame\. The timecode isn't disrupted by an [input switch](scheduled-input-switching.md)\.

MediaLive looks at the input timecode again only if either of these situations occurs:
+ You enabled timecode synchronization when you set up the timecode source, and a drift occurs\.
+ You have enabled pipeline locking and MediaLive determines a need to resynchronize the pipelines\. 

**Pausing and unpausing**

If you pause the channel, MediaLive continues to encode frames, which it immediately discards\. But because MediaLive continues to encode, the timecodes continue to increment\. Therefore, when you unpause, there will be a timecode discontinuity in the output\.

**Stopping and restarting**

If you stop and restart the channel, MediaLive follows the behavior dictated for the timecode source:
+ If the source is UTC clock or zero\-based, MediaLive applies the relevant timecode to the first output frame\.
+ If the source is embedded, MediaLive samples the timecode in the input again\. The situation might arise where the first time you started the channel with the source set to embedded, MediaLive didn't find an embedded timecode and therefore used system clock\. But the next time you start the channel, MediaLive might find an embedded timecode \(perhaps there was an input switch\)\. In this case, MediaLive uses that embedded timecode for the first output frame\.
# About the synchronization threshold<a name="timecode-sync"></a>

The **Sync threshold** synchronizes the output timecode with the input timecode\. Drift can occur in several ways\. For example, processing issues can occur that cause MediaLive to drop or repeat frames to compensate\. Or there might be discontinuities in the input timecode stream\.

**Purpose of Synchronization**

Synchronization is useful if it is important for your workflow that the output timecode \(that MediaLive generates\) match the original input timecode\. 
+ Matching might be important if you know that the downstream system must identify specific frames\. 

  Typically, the downstream system has already identified these frames based on the original input timecode\. Therefore, the output timecode must match the original input timecode, in order for the downstream system to find the desired frame\.
+ Matching isn't important if the main purpose of the output timecode is simply to uniquely identify each output frame\.

**How Synchronization Works**

After the input timecode and the output timecode have drifted apart by the specified number of frames, MediaLive inserts a discontinuity in the output timecode sequence, and sets the output timecode to match the current input timecode\.

The main drawbacks of synchronizing are that it introduces timecode discontinuities into the metadata, and that it can't guarantee that each output timecode is unique\. 
# Fields for ID3 segment tags<a name="schedule-fields-for-id3-segment-tags"></a>

This table shows the fields that apply for an action to insert ID3 segment tags\.


| Field | Description | 
| --- | --- | 
| Action type | HLS ID3 Segment Tagging\. | 
| Action name | A name for the segment tag\.  | 
|  Start type  | Fixed or Immediate\. | 
| Date and time |  If the **Start type** is **Fixed**, specify the UTC start time for the ID3 segment tag\. The time should be at least 15 seconds in the future\. Note that the time is the wall clock time, not the timecode in the input\.  | 
| Tag | The content of the tag\. The content is plaintext\. The content can include MediaLive [variable data](variable-data-identifiers.md)\. In the following example, the content consists of the date and time, and the current segment number\. The tag contents are different in each segment\.**$dt$\-$sn$** | 
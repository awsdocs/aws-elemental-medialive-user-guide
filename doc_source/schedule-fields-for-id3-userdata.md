# Fields for ID3 metadata<a name="schedule-fields-for-id3-userdata"></a>

This table shows the fields that apply for an action to insert one ID3 metadata\.


| Field | Description | 
| --- | --- | 
| Action type | HLS Timed Metadata\. | 
| Action name | A name for the metadata item\. You might want to design a convention for naming ID3 metadata items, such as id3\_metadata\-<UTC time>\. | 
|  Start type  | Fixed or Immediate\. | 
| Date and time |  If the **Start type** is **Fixed**, specify the UTC start time for the ID3 metadata item\. The time should be at least 15 seconds in the future\. Note that the time is the wall clock time, not the timecode in the input\.  | 
| Id3 | The ID3 metadata\. The metadata must be fully formed \(including both a header and a frame, as per the ID3 specification\) and must be encoded as base64\.  | 
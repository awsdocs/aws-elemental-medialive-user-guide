# How SCTE\-35 events are handled in manifests and sparse tracks<a name="how-scte-35-events-are-handled-in-manifests"></a>

When manifest decoration or sparse track is enabled, MediaLive inserts up to three types of information\. The triggers for inserting this information depend on the mode\. 

## Types of information<a name="manifest-types-of-info"></a>


| Type of instruction | When inserted | 
| --- | --- | 
| Base64 | Information about all SCTE\-35 messages in the output is incorporated into the manifest; the entire SCTE\-35 message is added in base64 format\. | 
| Cue\-out, cue\-in | SCTE\-35 messages that are ad avails result in the insertion of cue\-out, cue\-in instructions\. | 
| Blackout |  Only applies to the SCTE\-35 Enhanced ad marker style \(for HLS output; see [Enabling decoration – HLS](procedure-to-enable-decoration-hls.md)\)\. SCTE\-35 messages that are *not *ad avails result in the insertion of blackout start/end instructions, assuming that blackout is enabled\. If blackout is not enabled, these instructions are not inserted\.  | 

## Splice insert mode<a name="splice-insert-mode"></a>


**Message type ID: splice insert**  

| Segmentation Type ID | Base64 | Cue\-out, Cue\-in | Blackout | 
| --- | --- | --- | --- | 
| No segmentation descriptor present | Yes | Yes |   | 
| Provider advertisement | Yes | Yes |   | 
| Distributor advertisement | Yes | Yes |   | 
| Placement opportunity | Yes | Yes |   | 
| Break | Yes | Yes |  | 
| Other: Programs, Chapters, Network, Unscheduled | Yes |   | Yes | 


**Message type ID: time signal**  

| Segmentation type ID | Base64 | Cue\-out, cue\-in | Blackout | 
| --- | --- | --- | --- | 
| Provider advertisement | Yes | Yes |   | 
| Distributor advertisement | Yes | Yes |   | 
| Placement opportunity | Yes | Yes |   | 
| Break | Yes | Yes |  | 
| Other: Programs, Chapters, Network, Unscheduled | Yes |   | Yes | 

For example, read the first line in the first table as follows: When a splice insert \(with no segmentation descriptor\) is encountered, the base64 and cue\-out, cue\-in information will be inserted in the manifest; blackout information will not be inserted\.

## Timesignal APOS mode<a name="timesignal-apos-mode"></a>


**Message type ID: splice insert**  

| Segmentation type ID | Base64 | Cue\-out, cue\-in | Blackout | 
| --- | --- | --- | --- | 
| No segmentation descriptor present | Yes |   |   | 
| Provider advertisement | Yes |   |   | 
| Distributor advertisement | Yes |   |   | 
| Placement opportunity | Yes |   |   | 
| Break | Yes |  |  | 
| Other: Programs, Chapters, Network, Unscheduled | Yes |   |   | 


**Message type ID: Time signal**  

| Segmentation type ID | Base64 | Cue\-out, cue\-in | Blackout | 
| --- | --- | --- | --- | 
| Provider advertisement | Yes |   |   | 
| Distributor advertisement | Yes |   |   | 
| Placement opportunity | Yes | Yes |   | 
| Break | Yes | Yes |  | 
| Other: Programs, Chapters, Network, Unscheduled | Yes |   | Yes | 

For example, read the first line in the first table as follows: When a splice insert \(with no segmentation descriptor\) is encountered, the base64 information will be inserted in the manifest, and cue\-out, cue\-in information and blackout information will not be inserted\.
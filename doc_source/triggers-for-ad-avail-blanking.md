# Triggers for Ad Avail Blanking<a name="triggers-for-ad-avail-blanking"></a>

For ad avail blanking, the ad avail mode that you set controls which SCTE\-35 events result in the blanking of the content\.

## Triggers in Splice Insert Mode<a name="triggers-splice-insert-mode"></a>

This section describes which message type and segmentation type combination is blanked by ad avail blanking when the Ad Avail mode is Splice Insert mode\. 


**Message Type ID: Splice Insert**  

| Segmentation Type ID | Blanked | 
| --- | --- | 
| No segmentation descriptor present | Yes | 
| Provider advertisement | Yes | 
| Distributor advertisement | Yes | 
| Placement opportunity | Yes | 
| Other: Programs, Chapters, Network, Unscheduled | No | 


**Message Type ID: Time Signal**  

| Segmentation Type ID | Blanked | 
| --- | --- | 
| Provider advertisement | Yes | 
| Distributor advertisement | Yes | 
| Placement opportunity | Yes | 
| Other: Programs, Chapters, Network, Unscheduled | No | 

## Triggers in Timesignal APOS Mode<a name="triggers-timesignal-mode"></a>

This section describes which message type/segmentation type combination is blanked by ad avail blanking when the Ad Avail mode is Timesignal with APOS mode\. 


**Message Type ID: Splice Insert**  

| Segmentation Type ID | Blanked | 
| --- | --- | 
| No segmentation descriptor present | No | 
| Provider advertisement | No | 
| Distributor advertisement | No | 
| Placement opportunity | No | 
| Other: Programs, Chapters, Network, Unscheduled | No | 


**Message Type ID: Time Signal**  

| Segmentation Type ID | Blanked | 
| --- | --- | 
| Provider advertisement | No | 
| Distributor advertisement | No | 
| Placement opportunity | Yes | 
| Other: Programs, Chapters, Network, Unscheduled | No | 
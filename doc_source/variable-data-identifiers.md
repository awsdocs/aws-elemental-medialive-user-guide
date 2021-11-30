# Reference: identifiers for variable data<a name="variable-data-identifiers"></a>

Identifiers for variable data are `$` codes that you can include in a field value to represent variable data\. Typically, MediaLive resolves the variable data \(for example, `$dt$` for the date and time\) when you run the channel\. For example, `$dt$` resolves to the current date and time\.

When you use these identifiers, make sure that the channel doesn't end up with two \(or more\) outputs with identical destinations\. If that happens, the channel passes validation upon creation, but fails on start\. 

The following sections describe the variable identifiers that MediaLive supports, and the rules for where you can use these identifiers\.

## Supported variable data<a name="supported-variable-identifiers"></a>

MediaLive supports the variable data identifiers listed in the following table\. In each row, the first column specifies the string to enter in a field\. The second column specifies the format of the data after MediaLive has resolved the variable\. The third column describes the data\.


| Identifier | Format | Description | 
| --- | --- | --- | 
| $dt$ | YYYYMMDDTHHMMSS |  For HLS outputs, the UTC date and time of each segment\. For all other outputs, the UTC date and start time of the channel\.  | 
|  $d$ | YYYYMMDD |  For HLS outputs, the UTC date and time of each segment\. For all other outputs, the UTC date when the channel starts\.  | 
| $t$ | HHMMSS |  For HLS outputs, the UTC time of each segment\. For all other outputs, the UTC start time of the channel\.  | 
| $rv$ | Kb | Video bitrate\. | 
| $ra$ | Kb | Total of all audio bitrates in the output\. | 
| $rc$ | Kb | Container bitrate for the output, or the sum of video and all audio bitrates for the output, if the container bitrate is not specified\. | 
| $w$ | Pixels | Horizontal resolution\. | 
| $h$ | Pixels | Vertical resolution\. | 
| $f$ | Integer | FPS frame rate without decimal places\. For example, “23\.976” appears as “23”\. | 
| $$ | $ | Escaped $\. | 
| $sn$ | Integer, fixed length | Number of the segment of the video in the output\.  | 
| %0n | Padding modifier | Modifier for any data identifier\. The modifier pads the resolved value with leading zeros\. The format is%0n, where n is a number\. For example, to ensure the resolved value in the `$h$` identifier is 5 characters long, specify the identifier as `$h%05$`\. If the vertical resolution is “720”, then the resolved, padded value is “00720”\. | 

## Rules for using variable data<a name="rules-variable-identifiers"></a>

This table describes where you can use the variable data identifiers from the previous table\. In each row, the first two columns specify where you can use identifiers\. The third column specifies which identifiers you can use in that location\.


| Object | Field | Acceptable Identifiers | 
| --- | --- | --- | 
| Channel – Archive, HLS, Microsoft Smooth output groups | Destination field in an Output group | $dt$, $d$, $t$ | 
| Channel – Archive, Microsoft Smooth output groups | Name modifier field in an Output | All except $ra$, $rc$, $sn$  | 
| Channel – HLS output groups | Name modifier field in an Output | All except $sn$  | 
| Channel – Archive, Microsoft Smooth output groups | Segment modifier field in an Output | All except $ra$, $rc$, $sn$ | 
| Channel – HLS output groups | Segment modifier field in an Output | All except $sn$ | 
| Schedule – HLS ID3 Segment Tagging action | Tag field | All | 
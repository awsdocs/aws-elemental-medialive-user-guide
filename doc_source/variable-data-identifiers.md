# Reference: Identifiers for Variable Data<a name="variable-data-identifiers"></a>

Identifiers for variable data are $ codes that you can include in a field value to represent variable data\. Typically, the variable data \(for example, $d$ for the date\) is resolved when you run the channel\. You can include them in any of the fields that make up part of the output destination:

+ Destination in Output group

+ Name modifier in Output

+ Segment modifier in Output

At runtime, the identifier is resolved to the appropriate data\. For example, $dt$ resolves to a date and time\.

Be careful when using these identifiers to make sure that the channel does not end up with two \(or more\) outputs with identical destinations\. If this were to happen, the channel would pass validation upon creation, but it would fail on start\. 


| Identifier | Format | Description | 
| --- | --- | --- | 
| $dt$ | YYYYMMDDTHHMMSS | UTC date and time of the start time of the channel \(for all outputs except HLS\) or the date and time of each segment \(for HLS outputs\) | 
|  $d$ | YYYYMMDD | UTC date of the start time of the channel \(for all outputs except HLS\) or the date and time of each segment \(for HLS outputs\) | 
| $t$ | HHMMSS | Start time of the channel \(for all outputs except HLS\) or the time of each segment \(for HLS outputs\) | 
| $rv$ | Kb | Video bitrate | 
| $ra$ | Kb | Total of all audio bitrates in the output\. | 
| $rc$ | Kb | Container bitrate for the output, or the sum of video and all audio bitrates for the output, if container bitrate is not specified\. | 
| $w$ | Pixels | Horizontal resolution | 
| $h$ | Pixels | Vertical resolution | 
| $f$ | Integer | FPS Framerate without decimal places\. For example “23\.976” appears as “23” | 
| $fn$ | Filename | Name of input file, excluding the extension $ex$ Extension Extension of the output file | 
| $$ | $ | Escaped $ | 
| %0n | Padding modifier | Modifier for any data identifier\. The modifier pads the resolved value with leading zeros\. Format is %0n, where n is a number\. For example, to ensure the resolved value in the $h$ identifier is 5 characters long, specify the identifier as $h%05$\. If the vertical resolution is “720”, then the resolved, padded value is “00720” | 

The rules for which identifiers can be used in a given destination field depend on the output type:


| Field | Applicable Output Types | Acceptable Identifiers | 
| --- | --- | --- | 
| Destination in Output group | Archive, HLS, Microsoft Smooth | $dt$, $d$, $t$, $fn$ | 
| Name modifier in Output | Archive, Microsoft Smooth | All except $ra$ and $rc$ | 
| Name modifier in Output | HLS | All | 
| Segment modifier in Output | Archive, Microsoft Smooth | All except $ra$ and $rc$ | 
| Segment modifier in Output | HLS | All | 
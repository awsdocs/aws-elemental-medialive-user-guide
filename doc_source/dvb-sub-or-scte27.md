# Information for DVB\-Sub or SCTE\-27<a name="dvb-sub-or-scte27"></a>

DVB\-Sub and SCTE\-27 formats are supported only in TS inputs\. You must specify the location of the captions by completing the **PID** or **Language** code fields in one of these ways\.


****  

| PID | Language Code | Result | 
| --- | --- | --- | 
| Specified | Blank | Extracts captions from the specified PID\. | 
| Blank | Specified | Extracts the specified language, whichever PID that happens to be in\. | 
| Specified | Specified | Extracts captions from that PID; the language is informational\. | 
| Blank | Blank | Valid only if the source is DVB\-Sub and the output is DVB\-Sub\. With this combination of PID and Language, all input DVB\-Sub PIDs are included in the output\.Not valid for SCTE\-27\. | 
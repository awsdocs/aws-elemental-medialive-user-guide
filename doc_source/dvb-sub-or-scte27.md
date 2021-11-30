# Information for DVB\-Sub or SCTE\-27<a name="dvb-sub-or-scte27"></a>

DVB\-Sub and SCTE\-27 formats are supported only in RTP inputs\. 
+ All DVB\-Sub content is passed through, regardless of selectors\.
+ You must specify the location of the captions for SCTE\-27\.

  Complete the **PID** or **Language** code fields in one of the ways described in the following table\. Each row in the table describes a valid way to complete these two fields\.  
****    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/dvb-sub-or-scte27.html)
+ If you plan to convert the captions to WebVTT, you must also specify the language of the captions\.

  Complete the **OCR language** field to specify the language of the captions specified by this selector\.

  MediaLive ignores any value in this field if you aren't converting the captions to WebVTT\.
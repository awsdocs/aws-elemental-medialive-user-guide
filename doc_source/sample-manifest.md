# Sample manifest<a name="sample-manifest"></a>

This sample manifest contains the following elements:
+ Two video outputs, as indicated by the presence of two `EXT-STREAM-IN`F lines \(the last two lines in the example\)\.
  + The first video output has a low bandwidth\. As indicated by the `AUDIO` parameter, it is associated with *audio1*\.
  + The second video output has a higher bandwidth\. As indicated by the `AUDIO` parameter, it is associated with *audio2*\.
+ Four audio outputs, as indicated by the presence of four `EXT-X-MEDIA` lines with `TYPE=AUDIO`\. In each audio output, the values for the parameters come from the following fields in each audio output in the channel:
  + `Type` is always `Audio`\.
  + `GROUP-ID` is from the **Audio Group ID** field in the **Output settings** section\.
  + `LANGUAGE` is from the **Language Code** field in the **Stream settings** section\.
  + `NAME` is from the **Stream Name** field in the **Stream settings** section\.
  + `AUTOSELECT` and `DEFAULT` are from the **Alternate Audio Track Type** field in the **Output settings** section\.
  + `URI` is from the **Destination** field in the output group\. 

  For information on all these fields, see [Step 4: Create the audio outputs](ARG-step-create-audio.md)\.
+ Two audio rendition groups\. The audio renditions groups don't have their own lines in the manifest\. Their existence is implied by the presence of `GROUP-ID` parameters in the audio lines\. 
+ Two captions streams, as indicated by the presence of two `EXT-X-MEDIA` lines with `TYPE=SUBTITLES`\. 

```
     
#EXTM3U
#EXT-X-MEDIA:TYPE=AUDIO,GROUP-ID="AAC group",LANGUAGE="eng",NAME="English",AUTOSELECT=YES,\ DEFAULT=YES,URI="eng1/aac-en.m3u8"
#EXT-X-MEDIA:TYPE=AUDIO,GROUP-ID="AAC group",LANGUAGE="fre",NAME="français",AUTOSELECT=YES,\ DEFAULT=NO,URI="fr1/aac-fr.m3u8"
#EXT-X-MEDIA:TYPE=AUDIO,GROUP-ID="DD group",LANGUAGE="eng",NAME="English",AUTOSELECT=YES,\ DEFAULT=YES,URI="eng2/dd-en.m3u8"
#EXT-X-MEDIA:TYPE=AUDIO,GROUP-ID="DD group",LANGUAGE="fr",NAME="français",AUTOSELECT=YES,\ DEFAULT=NO,URI="fr2/dd-fr.m3u8"
            
#EXT-X-MEDIA:TYPE=SUBTITLES,GROUP-ID="subs",LANGUAGE="eng",NAME="English",
DEFAULT=YES,AUTOSELECT=YES,FORCED=NO,URI="sub-en.m3u8"
#EXT-X-MEDIA:TYPE=SUBTITLES,GROUP-ID="subs",LANGUAGE="fra",NAME="French",
DEFAULT=YES,AUTOSELECT=YES,FORCED=NO,URI="sub-fr.m3u8"
            
#EXT-X-STREAM-INF:PROGRAM-ID=1,BANDWIDTH=195023,CODECS="avc1.42e00a,mp4a.40.2",AUDIO="AAC group"
lo/prog-index.m3u8,SUBTITLES="subs",URI="curling-hi.m3u8"
#EXT-X-STREAM-INF:PROGRAM-ID=1,BANDWIDTH=591680,CODECS="avc1.42e01e,mp4a.40.2",AUDIO="DD group"
hi/prog-index.m3u8,URI="curling-lo.m3u8"
```
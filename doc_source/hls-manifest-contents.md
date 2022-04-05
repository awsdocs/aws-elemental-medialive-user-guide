# Fields for contents of manifests<a name="hls-manifest-contents"></a>

The following fields in the **HLS output group – Manifests and Segments** section configure the information to include in the HLS child manifests:
+ **Output selection**
+ **Mode**
+ **Stream inf resolution**
+ **Manifest duration format**
+ **Num segments**
+ **I\-frame only playlists** – This field is used to implement trick\-play via I\-frames\. For more information, see [Trick\-play track via I\-frames](trick-play-i-frames.md)\.
+ **Program date time \(PDT\)** – This field is used to include or exclude the `EXT-X-PROGRAM-DATE-TIME` tag in manifest files\. The tag information helps downstream players to synchronize the stream to the source that's selected in the **PDT clock** field\.
+ **Program date time \(PDT\) period** – This field is used to set the time interval for insertion of `EXT-X-PROGRAM-DATE-TIME` tags, in seconds\.
+ **Program date time \(PDT\) clock** – This field is used to select the time source of the PDT\. Output timecode or UTC time can be selected\.
+ **Client cache**
+ **Timestamp delta microseconds**
+ **Codec specification**
+ **Manifest compression**

For details about a field, choose the **Info** link next to the field in the MediaLive console\. 
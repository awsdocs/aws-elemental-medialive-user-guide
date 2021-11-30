# Channel input—HLS pull input<a name="input-hls-pull"></a>

To verify that the input is set up correctly, look at the **Input sources** section\. It shows the locations of the source video\. You specified these locations when you created the input:
+ If the channel is set up as a standard channel, you specified two locations\.
+ If the channel is set up as a single\-pipeline channel, you specified one\.

For example, for an HTTPS pull:

**https://203\.0\.113\.13/sports/curling\.m3u8** and

**https://203\.0\.113\.54/sports/curling\.m3u8** 

Or, for a pull from an AWS Elemental MediaStore container:

**mediastoressl://eri39n\.data\.mediastore\.us\-west\-2\.amazonaws\.com/sports/canada/curling\.m3u8**

 and

**mediastoressl://21lu05\.data\.mediastore\.us\-west\-2\.amazonaws\.com/sports/canada/curling\.m3u8** 

Or, for a pull from an Amazon S3 bucket:

**s3ssl://DOC\-EXAMPLE\-BUCKET/filler\-videos/main/oceanwaves\.mp4** and

**s3ssl://DOC\-EXAMPLE\-BUCKET/filler\-videos/redundant/oceanwaves\.mp4**
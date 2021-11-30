# Channel input—MP4 pull input<a name="input-mp4-pull"></a>

To verify that the input is set up correctly, look at the **Input destinations** section\. It shows the locations of the source video\. You specified these locations when you created the input:
+ If the channel is set up as a standard channel, you specified two locations\.
+ If the channel is set up as a single\-pipeline channel, you specified one\. 

The format of the location depends on the type of upstream system:
+ For an upstream system that uses HTTP or HTTPS, the location is an HTTP or HTTPS URL\. For example:

  **https://203\.0\.113\.31/filler\-videos/oceanwaves\.mp4**

  **https://203\.0\.113\.52/filler\-videos/oceanwaves\.mp4**
+ For a file that is stored on Amazon S3, the location is the bucket name and object for the file\. For example:

  **s3ssl://DOC\-EXAMPLE\-BUCKET/filler\-videos/main/oceanwaves\.mp4**

  **s3ssl://DOC\-EXAMPLE\-BUCKET/filler\-videos/redundant/oceanwaves\.mp4**
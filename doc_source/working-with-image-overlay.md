# Working with Image Overlays<a name="working-with-image-overlay"></a>

You can use the static image overlay feature to superimpose a static image onto a video in an MediaLive channel\. A static image is a still image that doesn't have motion\. You prepare the image and store it outside of MediaLive\. You then use the [schedule](working-with-schedule.md) feature in MediaLive to set up a timetable that specifies when images \(up to eight different images\) will be shown in the running channel, and when each will be hidden\. 

## Examples<a name="static-image-examples"></a>

**Example 1**  
You want to insert a static image overlay at a specific time and run it for 10 seconds\. You want the image overlay to appear in the lower\-right corner of the video frame\. You want the image overlay to be 50% opaque and to fade in from nothing to full 50% opacity over 2 seconds, then to fade out to nothing starting 2 seconds before the end of the insertion\.

**Example 2**  
You want to insert two static image overlays so that they both appear in the video frame either at the same time or with some overlap\. You want the display of the image overlays to slightly overlap so that one image overlay appears in a location and, while that image overlay is still showing, another image overlay appears in another location\. If the locations overlap either partially or completely, you want to specify which image overlay appears on top\.

## Features of the Static Image Overlay<a name="features-static-overlay"></a>

The image that you overlay on a video can be a \.bmp, \.png, or \.tga file\. 

You can insert up to eight images at one time\. Each image is a separate "layer\." You can set up the overlays to all appear on the underlying video at the same time \(or not\), and you can set them up to physically overlap each other \(or not\)\. 

You can configure each image overlay with a start time and duration\. You can insert the image overlay at any position on the video frame, as specified by x/y coordinates\. You can configure with an opacity and with fade\-in and fade\-out\. 

The image is handled as follows:
+ The image is overlaid on the underlying video pixel for pixel, without scaling\. 

  If the overlay is larger than the underlying video or overruns an edge of the underlying video, and if the system can identify this error at channel creation time, you will see an error message at that time\. 

  If the system can't identify the error in advance, an error message will appear while the channel is running\. The channel won't stop, but the overlay request will fail\.
+ The image is overlaid before creation of individual output encodes \(with their different resolutions and video quality\)\. This means that if the underlying video is scaled for a particular output encode, then the image is similarly scaled\. 
+ The image is inserted in all outputs\.

## Step 1: Prepare the Static Image Overlay File<a name="prepare-static-overlay"></a>

You must prepare each image overlay that you want to use in your channels\. The overlays are stored outside of MediaLive, for example, in an Amazon S3 bucket\. An image overlay doesn't belong to MediaLive or to a specific channel in MediaLive\. Rather, the image overlays are used by MediaLive\.

Follow this procedure to prepare overlays when you need them\. 

**To prepare the overlay file**

1. Create a file with the following characteristics:
   + File type: A \.bmp, \.png, or \.tga file\.
   + Aspect ratio: The overlay can have any aspect ratio\. It doesn't have to match the aspect ratio of the underlying video\. 
   + Size, in pixels: The overlay can be any resolution \(size in pixels\) up to the same size as the underlying video\. 

1. If you use a graphics program that outputs channels, set up to output the alpha channel\. This ensures that the image overlay doesn't appear in a black or white box\.

1. Place the prepared file in a location that is accessible to the MediaLive\. You can specify the location in one of four ways: 
   + Amazon S3 bucket, using SSL\. For example: 

     `s3ssl://company.test/sample_bucket/overlay.png`
   + Amazon S3 bucket, without SSL\. For example:

     `s3://company.test/sample_bucket/overlay.png`
   + Accessible URL that requires SSL\. For example:

      `https://203.0.113.0/corporate_logos/large.bmp`
   + Accessible URL without SSL\. For example:

      `http://203.0.113.254/corporate_logos/high_res.bmp`

1. Make a note of the location\. You will need it later\.

## Step 2: Insert the Overlay<a name="inserting-overlay"></a>

You insert an overlay in the video by creating an insert action in the channel schedule\. For detailed information, see [Working with the AWS Elemental MediaLive Schedule](working-with-schedule.md) and [Creating Actions in the Schedule \(Console\)](schedule-using-console-create.md)\.

The schedule is a timetable that is attached to each channel\. The schedule is designed to let you specify actions to perform on the channel at a specific time\. So with an image overlay, for example, you create actions in the schedule to specify that a specific image will be overlaid on the underlying video at a specific time, for a specific duration\. 

When a channel is running, its configuration does not and cannot change\. So the channel schedule lets you apply dynamically occurring actions to the channel without having to stop it and reconfigure\.
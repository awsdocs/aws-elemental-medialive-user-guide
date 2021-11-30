# Step 1: Prepare the motion graphic asset<a name="mgi-prepare-asset"></a>

You use an authoring system to create the asset and to manage the content, including implementation of features such as fade or opacity\. 

MediaLive's role in displaying the graphics overlay is limited to rendering the asset, and to inserting it and removing it from the video at the specified times\. MediaLive doesn't provide any features for manipulating the motion graphic\.

**To prepare the motion graphic asset**

1. Use the authoring system to create the asset\. The HTML5 content must meet these requirements:
   + It can be any HTML5 authoring system that uses standard browser\-based rendering techniques\. 
   + It can use any HTML5 tags except video and audio\.
   + It can incorporate Javascript to interact with a backend system that provides the ability to dynamically control the asset that is being published to the source URL\. 
   + You should size the content to match the width and height of the largest video rendition in your channel\. MediaLive can't change the resolution of the asset to fill the frame, although it will resize content down to fit a smaller video rendition without cropping\.

1. Publish the motion graphic asset to a source URL that is accessible via a public IP address\.

1. Make a note of the location\. You will need it when you add the schedule action\.

1. If the location of the motion graphics asset requires login in order to download files, obtain the required user name and password\. Make a note of the credentials\. You will need them when you add the schedule action\.
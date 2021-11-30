# Working with motion graphics overlays<a name="feature-mgi"></a>

You can use the motion graphics overlay feature to superimpose a motion image onto the video in a MediaLive channel\. The motion image is based on an HTML5 motion graphic asset\. 

To set up for motion graphics overlay, you must perform work in two areas: 
+ You must choose an *HTML5 authoring system*\. You must use this authoring system to prepare an HTML5 asset, and you must continually publish the asset to a location outside of MediaLive\. 
+ On MediaLive, you must enable motion graphics in each channel where you want to include a motion graphic overlay\.

After you have started the channel, you use the [schedule](working-with-schedule.md) feature in MediaLive to insert the motion graphic in the running channel\. As soon as the schedule receives the action, MediaLive starts to download and render the content\. It continually downloads and renders the content for as long as the motion graphics action is active\. At any time, you can deactivate the image by creating a deactivate action in the schedule\.

## Pricing<a name="mgi-pricing"></a>

There is a charge for running a channel that has the motion graphics overlay feature [enabled](mgi-prepare-channel.md)\. There is a charge even when there is no motion graphics overlay currently inserted in the channel\.

The charge is based on the largest video output in the channel\.

To stop this charge, you must disable the feature\.

For information on charges for using this mode, see the MediaLive price list\. https://aws\.amazon\.com/medialive/pricing/

**Topics**
+ [Pricing](#mgi-pricing)
+ [Step 1: Prepare the motion graphic asset](mgi-prepare-asset.md)
+ [Step 2: Enable the feature](mgi-prepare-channel.md)
+ [Step 3: Insert the overlay](mgi-insert-overlay.md)
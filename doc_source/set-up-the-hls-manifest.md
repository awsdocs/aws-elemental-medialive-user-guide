# Set up the HLS Manifest<a name="set-up-the-hls-manifest"></a>

If the captions are embedded captions and the output is HLS, you can choose to include caption language information in the manifest\.

1. In the HLS output group, for **Captions**, in **Caption language setting**, choose **Insert**\. Choosing this option inserts lines in the manifest for each embedded captions language\. It inserts as many lines as the mappings that you will add in the next step\. 

1. For **HLS settings**, in **Caption language mappings**, choose **Add caption language mappings**\.

1. Choose **Add caption language mappings** to add more groups, one for each embedded captions asset, to a maximum of four groups\.

1. Complete each group to identify the CC \(caption channel\) number and its language\. For example, if caption channel 1 is French, then set up the three fields with "1", "FRE", and "French"\. 

   The order in which you enter the languages must match the order of the captions in the source\. For example, if the captions are in the order French, then English, then Spanish, then Portuguese, then set up CC1 as French, CC2 as English, and so on\. If you do not order them correctly, the captions in the manifest will be tagged with the wrong languages\.
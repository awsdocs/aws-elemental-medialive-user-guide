# HLS Manifests \(Embedded Captions\)<a name="set-up-the-hls-manifest"></a>

If the captions are embedded captions and the output is HLS, you must include captions language information in the manifest\. If you don't include this information, the downstream player won't have information about the embedded captions\. 
+ In the HLS output group in Output groups, for **Captions**, in **Captions language setting**, choose **Insert**\. Choosing this option inserts lines in the manifest for each embedded captions language\. It inserts as many lines as the mappings that you will add in the next step\. 
+ Still in the HLS output group, for **HLS settings**, in **Captions language mappings**, choose **Add captions language mappings**\.
+ Choose **Add captions language mappings** again to add more mapping groups, one for each embedded captions asset, to a maximum of four groups\. For example, if the output embedded languages contain English, French, and Spanish, you need three mapping groups\.
+ Complete each mapping group to identify the CC \(caption channel\) number and its language\. For example, if captions channel 1 is French, then set up the three fields with "1", "FRE", and "French"\. 

  The order in which you enter the languages must match the order of the captions in the source\. For example, if the captions are in the order French, then English, then Spanish, then Portuguese, then set up CC1 as French, CC2 as English, and so on\. If you don't order them correctly, the captions in the manifest will be tagged with the wrong languages\.
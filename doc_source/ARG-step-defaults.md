# Step 2: Determine Defaults and Selection Rules<a name="ARG-step-defaults"></a>

As the second part of planning the audio rendition group, you should identify the following:
+ The rendition \(if any\) that is the default\.
+ How auto\-selection will work for the non\-default renditions\. 

This information might be useful to the client player that is playing this media asset\. 
+ If a client player is configured with an audio preference \(for example, Spanish\) and that preference is not available, the player can use this information to select an audio\. 
+ Or if the client player is not configured with any audio preference, the client player can use this information to select an audio\.



\(If the preference that is configured in the client player is available, the player ignores this information and selects that preference\.\)

**To determine defaults and auto\-selection behavior**
+ For each audio rendition in the rendition group, choose the behavior from the following table\. Each audio can have a different value\. 

  Each row in the following table describes a different behavior\.    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/ARG-step-defaults.html)

**Example 1**  
In this example you want to set up the audio rendition group so that the client player can auto\-select any of the renditions\. You also want a default audio in the rendition group in case the client player is not set up with a default\.  
+ Set only one audio rendition to *Alternate Audio, Auto Select, Default*\.
+ Set every other audio rendition to *Alternate Audio, Auto Select, Not Default*\.
+ Optionally, if you have an audio rendition that plays when the bandwidth is so low that the video cannot be delivered, then set that audio rendition to *Audio\-Only Variant Stream*\.

**Example 2**  
In this example you want to set up the audio rendition group so that the client player can auto\-select only specific renditions\. You also want a default audio in the rendition group in case the client player is not set up with a default\.  
+ Set only one audio rendition to *Alternate Audio, Auto Select, Default*\.
+ Set some of the other renditions to *Alternate Audio, Auto Select, Not Default*\.
+ Set some of the other renditions to *Alternate Audio, not Auto Select*\.
+ Optionally, if you have an audio rendition that plays when the bandwidth is so low that the video cannot be delivered, then set that audio rendition to *Audio\-Only Variant Stream*\.

**Example 3**  
In this example you want to set up the audio rendition group so that the client player can auto\-select any audio rendition it chooses\. You don't want a default audio rendition in the rendition group, so the client player always auto\-selects audio\.  
+ Set every audio rendition to *Alternate Audio, Auto Select, Not Default*\.
+ Optionally, if you have an audio rendition that plays when the bandwidth is so low that the video cannot be delivered, then set that audio rendition to *Audio\-Only Variant Stream*\.
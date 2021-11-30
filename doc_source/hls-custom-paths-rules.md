# Rules for custom paths<a name="hls-custom-paths-rules"></a>

Share the following rules with your contact person at the downstream system\.

The general rule is that it’s the responsibility of the downstream system to ensure that the custom paths work in their environment\. MediaLive doesn’t validate the values in any way\. Therefore:
+ If the protocol is specified \(it is optional\), it must be identical to the protocol that you specified in the **Destination URL** fields\.
+ The **Base URL manifest** and **Base URL content** fields for the same pipeline can have the same value or different values\. They can be the same or different in any portion \(the domain, path\)\.
+ The values can result in a relative path or an absolute path\. 
+ A relative path to the child manifest is always relative to the location of the main manifest\.
+ A relative path to the media files is always relative to the location of the child manifest\.
+ The paths must end with a slash\.
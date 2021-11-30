# Implementing a trick\-play track<a name="trick-play-solutions"></a>

Trick\-play is used in digital video players to mimic some capabilities of analog players, including fast\-forward and rewind capabilities\. These capabilities often include a trick\-play *track*—a visual cue for the person using the video player\. In AWS Elemental MediaLive, you can include track assets in the output group\. The downstream system for that output group can use these assets to implement the visual cue in their trick\-play implementation\. 

MediaLive provides two methods for including these assets:
+ An I\-frame\-only manifest that conforms with the HLS specification\.
+ A trick\-play track that conforms with the Image Media Playlist specification, version 0\.4\. 

MediaLive supports these methods as follows:
+ In HLS output groups, MediaLive supports both methods\.
+ In MediaPackage output groups, MediaLive supports trick\-play via the Image Media playlist specifiction

## Choosing an implementation of trick\-play track<a name="trick-play-choosing"></a>

You can follow one or both trick\-play methods in the same output group\. 

Before you follow either method, contact the downstream system for the output group to find out how they implement trick\-play\. Find out the following: 
+ Can the downstream system support a trick\-play track? If so, which trick\-play specification does it follow?
+ Is the supported implementation required or optional? Both of these implementations introduce specific lines into the HLS manifest\. If the lines are absent, the downstream system will fail to handle the output from MediaLive?

  It is likely that the downstream system considers both of these implementations to be optional\.
+ If you choose the I\-frame\-only manifest method, confirm that the downstream system supports the method according to the HLS specification\. If the downstream system has a variation, it's possible that the downstream system won't be able to handle the output from MediaLive\. MediaLive doesn't support customizations of the method\.
+ If you choose the image media playlist method, confirm that the downstream system supports the method according to the Image Media Playlist specification\. If the downstream system has a variation, it's possible that the downstream system won't be able to handle the output from MediaLive\. MediaLive doesn't support customizations of the implementation\. 

**Topics**
+ [Choosing an implementation of trick\-play track](#trick-play-choosing)
+ [Trick\-play track via I\-frames](trick-play-i-frames.md)
+ [Trick\-play track via the Image Media Playlist specification](trick-play-roku.md)
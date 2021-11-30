# Combining redundant manifests with other features<a name="hls-redundant-manif-combine"></a>

**Combining redundant manifests and custom path feature**

You can set up custom paths in redundant manifests\. Make sure you follow the rules [for custom paths](hls-custom-paths-rules.md) and for redundant manifests for your downstream system—either an [Akamai CDN](hls-redundant-manif-akamai.md) or [another downstream system](hls-redundant-manif-most-systems.md)\.

**Combining redundant manifests with audio rendition groups**

**Note**  
The information in this section assumes that you are familiar with the manifests for audio rendition groups\. For more information, see [Sample manifest](sample-manifest.md)\.

If you have set up redundant manifests and you have an audio rendition group, MediaLive automatically adjusts the references to the audio rendition groups in the parent manifests\.

In each pair of lines \(for example, the `#EXT-X-STREAM-INF` for the high\-resolution video\), MediaLive adjusts the name of the rendition groups\. In this way, the references to the rendition groups are different for each pipeline, which ensures that when the client player reads the manifest, it chooses the video and the audio from the same pipeline\. 

The `#EXT-X-STREAM` for the video for pipeline 0\. Note the value for *AUDIO*:

```
#EXT-X-STREAM-INF:BANDWIDTH=541107,...AUDIO="aac-audio-0", ... 
```

 The `#EXT-X-STREAM` for the video for pipeline 1\. Note the value for *AUDIO*:

```
#EXT-X-STREAM-INF:BANDWIDTH =541107, ...AUDIO="aac-audio-1",... 
```
# The media contents of an HLS manifest<a name="hls-rm-manifests-contents"></a>

Setting up redundant manifests changes the contents of the HLS manifest\. It changes the media information \(the video, audio, and captions information\) inside the manifests\. All of this information appears as `#EXT-X-STREAM-INF` tags\.

The following sections describe the number of these tags and the contents of these tags in a standard \(not redundant\) manifest and in a redundant manifest\.

## What a standard manifest looks like<a name="hls-redundant-manif-what-standard-like"></a>

With a standard channel, there are two pipelines\. Each pipeline produces its own set of manifests\. Therefore, for pipeline 0, there is one main manifest, one set of child manifests, and one set of media files\. Similarly, pipeline 1 has the same set of files\. The manifests reference only the files for their own pipeline\.

The video information in the main manifest for each pipeline might look like this:

```
#EXT-X-STREAM-INF:BANDWIDTH=629107 ... 
curling-high.m3u8
```

## What a redundant manifest looks like<a name="hls-redundant-manif-what-redundant-like"></a>

When the redundant manifest feature is enabled, each main manifest references the child manifests for its own pipeline and for the other pipeline\. 

This feature doesn’t affect child manifests\. Child manifests only reference their own media files\.

Following is an example of how the video information in the manifest might appear\. Assume that the baseFilename for pipeline 0 is *first\-curling* and for pipeline 1 it is *other\-curling*\. 

The manifest for pipeline 0 might look like this \(with the child manifest information for pipeline 0 appearing first\):

```
#EXT-X-STREAM-INF:BANDWIDTH=629107 ... 
first-curling-high.m3u8

#EXT-X-STREAM-INF:BANDWIDTH=629107 ... 
other-curling-high.m3u8
```

The video information in the manifest for pipeline 1 might look like this \(with the child manifest information for pipeline 1 appearing first\):

```
#EXT-X-STREAM-INF:BANDWIDTH=629107 ... 
other-curling-high.m3u8

#EXT-X-STREAM-INF:BANDWIDTH=629107 ... 
first-curling-high.m3u8
```
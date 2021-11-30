# Procedure to set up redundant manifests<a name="hls-rm-procedure"></a>

To set up redundant manifests, you turn on the feature in the output group\. You also make adjustments in the design of the output names and destination paths \(compared to HLS outputs that don't implement redundant manifests\)\.

The following field relates specifically to redundant manifests:
+ **HLS output group – Manifests and Segments – Redundant manifests** field

**To set up redundant manifests**

1. Speak to the downstream system to find out if they support redundant manifests\.

1. Read the information in [Fields for the output destination – sending to an HTTP server](hls-destinations-http.md)\. Manifests are considered to be output from MediaLive\. Therefore, the general rules about output destinations apply to redundant manifests\.

1. Design the URLs for the two pipelines\. There are special requirements for the URLs for the HLS files\. Read the appropriate section:
   + [Rules for most downstream systems](hls-redundant-manif-most-systems.md) 
   + [Rules for Akamai CDNs](hls-redundant-manif-akamai.md)

   These rules supplement the information in [Fields for the output destination – sending to an HTTP server](hls-destinations-http.md)\.

1. If you also need custom paths for manifests, make sure you read the information in [How custom paths work](hls-manifests-how-work.md#hls-custom-manifest-paths)\. You must consider the rules for custom paths when you design the URLs\.

1. In the **HLS output group** section, for **Manifest and segments**, for **Redundant manifest**, choose **ENABLED**\. This field applies to all outputs in the output group\.

1. Complete these fields, following your design:
   + **Output group – HLS group destination** section
   + **Output group – HLS settings – CDN** section
   + **Output group – Location – Directory structure **
   + **Output group – Location – Segments per subdirectory**
   + **HLS outputs – Output settings – Name modifier**
   + **HLS outputs – Output settings – Segment modifier**
   + **HLS output group – Location –Base URL Manifest** \(if you are also setting up custom paths\)
   + **HLS output group – Location – Base URL Content** \(if you are also setting up custom paths\) 

For information about how this feature changes the contents of the HLS manifests, see [The media contents of an HLS manifest](hls-rm-manifests-contents.md)\.

## The results of this setup<a name="hls-redundant-manif-results"></a>

Following is information about how redundant manifests work in three failure scenarios\.

### Scenario A – Input loss action is to emit output<a name="hls-redundant-manif-results-emit"></a>

If the input is lost on one of the pipelines and the [**Input loss action** field](hls-resiliency.md) is set to **EMIT\_OUTPUT**, MediaLive continues to update the parent and child manifests\. 

From the point of view of the downstream system, there is no change to the parent or child manifests for either pipeline\. The content inside the media files is filler content, but that doesn't affect how the downstream system reads the manifests\.

### Scenario B – Input loss action is to pause output<a name="hls-redundant-manif-results-pause"></a>

If the input is lost on one of the pipelines \(for example, on pipeline 0\) and the **Input loss action** field is set to **PAUSE\_OUTPUT**, MediaLive does the following:
+ It removes the listing for the child manifests for pipeline 0\. 
+ It sends a request to the child manifest location for pipeline 0 to delete the child manifests\.

The result for the downstream system that is reading the main manifest on pipeline 0: The system will no longer find a listing for the child manifests for pipeline 0\. The system will look in the pipeline 0 main manifest for an alternative child manifest\. If it finds the child manifest for pipeline 1, it will switch to reading that child manifest\. 

Downstream systems that are reading the main manifest for pipeline 1 are not affected because these systems are probably reading the child manifests for pipeline 1 \(because these appear first in the manifest\)\. 

### Scenario C – Pipeline failure<a name="hls-redundant-manif-results-pipeline-failure"></a>

It is also possible for a pipeline to fail\. This failure isn't the same as an input failure\. When a pipeline fails \(for example, pipeline 0\), the following happens:
+ Output stops\.
+ The main manifest for pipeline 0 doesn't get deleted\. It still contains a listing for the child manifests for pipeline 0\. 
+ The child manifests are not updated because no new media files are being produced\. The child manifests are *stale*\.
+ The main manifest for pipeline 1 doesn't change\. It still contains a listing for the child manifests for pipeline 0 \(and for pipeline 1\)\.

The result for the downstream system that is reading the main manifest for pipeline 0: The system will find a listing for child manifests for pipeline 0, but that manifest will be stale\. If the system can detect that the manifest is stale, it can return to the pipeline 0 main manifest and search for an alternative child manifest\. If it finds the child manifest for pipeline 1, it will switch to reading that child manifest\. 

Downstream systems that are reading the main manifest for pipeline 1 are not affected\. These systems are presumably reading the child manifests for pipeline 1 \(because these appear first in the manifest\)\.

**Note**  
If the downstream system for the HLS output is AWS Elemental MediaStore, you can set up MediaStore to delete stale inputs\. See [Components of an object lifecycle policy](https://docs.aws.amazon.com/mediastore/latest/ug/policies-object-lifecycle-components.html)\. After the child manifest has been deleted, MediaStore falls back to following the "manifest has been deleted" logic of scenario B\.
# Clean up scenarios for color space metadata<a name="color-space-cleanup-scenarios"></a>

This section describes recommended cleanup scenarios based on the following:
+ How you plan to handle the color space in the output
+ The quality of the color space metadata in the input\.

## Scenario A – Pass through accurate metadata<a name="color-space-scenario-pass"></a>

The details of this scenario are the following:
+ Intended handling in the output – Pass through the color space\.
+ Status of the input – The video content is any combination of color spaces—SDR, HDR, or both\. 
+ Status of the input color space metadata – The metadata is correct\. 

Recommendation:
+ **Color space **field – Set to **FOLLOW** 
+ **Color space usage **field – MediaLive ignores this field\.

During ingest, MediaLive will retain \(pass through\) the metadata\. 

## Scenario B – Convert accurate metadata<a name="color-space-scenario-convert"></a>

The details of this scenario are the following:
+ Intended handling in the output – Convert the color space and metadata\.
+ Status of the input color space – The video content is any combination of color spaces—SDR, HDR, or both\. 
+ Status of the input color space metadata – The metadata is correct\. 

Recommendation:
+ **Color space **field – Set to **FOLLOW** 
+ **Color space usage **field – MediaLive ignores this field\.

During ingest, MediaLive will retain \(pass through\) the metadata\. 

## Scenario C – Remove metadata<a name="color-space-scenario-remove"></a>

The details of this scenario are the following:
+ Intended handling in the output – Remove the color space metadata\.
+ Status of the input – The video content is any combination of color spaces—SDR, HDR, or both\. 
+ Status of the input color space metadata – The metadata can be of any quality\. 

Recommendation:
+ **Color space **field – Set to **FOLLOW** 
+ **Color space usage **field – MediaLive ignores this field\.

During ingest, MediaLive will retain \(pass through\) the metadata\. You plan to remove the metadata, so you don't care about its quality\.

## Scenario D – Correct the metadata<a name="color-space-scenario-correct"></a>

The details of this scenario are the following:
+ Intended handling in the output – Convert or pass through the color space\.
+ Status of the input – The video content is one color space\. For example, the content is all REC\_601\.
+ Status of the input color space metadata – Some of the metadata is missing, marked as *unknown*, or marked as a color space that MediaLive doesn't support\. 

  In addition, some of the metadata is wrong\. For example, it is marked as HDR10, but in fact, it is REC\_601\.

Recommendation:
+ **Color space **field – Set to the color space that has unacceptable metadata\. 
+ **Color space usage **field – Set to **FORCE**

During ingest, MediaLive will create metadata of the specified color space for all missing, unmarked, and unknown metadata\. 

It will also force all existing metadata to match the specified color space\. Therefore, all the content in the input will be consistently marked as belonging to one color space\.

## Scenario E – Correct the metadata in one color space<a name="color-space-scenario-correct-one"></a>

The details of this scenario are the following:
+ Intended handling in the output – Convert or pass through the color space\.
+ Status of the input – The video content is any combination of color spaces—REC\_601, REC\_709, HDR, and HLG\. 
+ Status of the input color space metadata – The metadata for the video content of one color space is a mixture of acceptable and unacceptable\. The metadata for that content is missing, marked as *unknown*, or marked as a color space that MediaLive doesn't support\. But in fact, all that content should be marked as one specific color space, for example, as REC\_601\.

  The metadata for content for any other color space is correct\. For example, the metadata for REC\_709 content and HDR10 content is correct\.

Recommendation:
+ **Color space **field – Set to the color space that has unacceptable metadata\. 
+ **Color space usage **field – Set to **FALLBACK**

During ingest, MediaLive will create metadata of the specific color space for all missing, unmarked, and unknown video content\. It will retain existing metadata\.

## Scenario F – Correct the metadata in multiple color spaces<a name="color-space-scenario-correct-multiple"></a>

The details of this scenario are the following:
+ Intended handling in the output – Convert or pass through the color space\.
+ Status of the input – The video content is in *more than one* color space\. For example, the content is a mix of REC\_601, REC\_709, and HDR10\.
+ Status of the input color space metadata – The metadata for one color space is missing, wrong, marked as *unknown*, or marked as a color space that MediaLive doesn't support\. For example, the color space is REC\_601, but its corresponding metadata is unreliable\.

  In addition, the metadata for one or more other color spaces is also missing, wrong, unknown, or not supported\. For example, the color space of that content is HLG, but its corresponding metadata is unreliable\.

Recommendation:

There is no way to clean up this content because you can only mark all the content as one type of color space\. But in this scenario, the metadata is incorrect in different types of color space\.

If you force the color space, some of it will be forced to be correct, but some of it will be forced to incorrect information\. Inaccurate metadata will result in an inaccurate conversion \(if you convert in the output\), or in an inferior viewing experience \(if you pass through in the output\)\.

The best recommendation we can provide is to remove the metadata on the output side—scenario C\.
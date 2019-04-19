# Sample Manifests \- HLS<a name="sample-manifests-hls"></a>

MediaLive supports the following HLS manifest styles for outputs:
+ Adobe
+ Elemental
+ SCTE\-35 Enhanced

This section describes the ad marker tagging for each style of output manifest\.

**Note**  
MediaLive doesn't interpret the ad avail decoration information in the manifest attached to the input source\.

## Ad Marker: Adobe<a name="sample-manifests-hls-adobe"></a>

Inserts a CUE: DURATION for each ad avail\. Does not insert any CUE\-OUT CONT \(continuation tags\) to indicate to a player joining midbreak that there is a current avail\. This does not insert a CUE\-IN tag at the end of the avail\.

**Structure**      
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/sample-manifests-hls.html)

**Tag Contents**  
+ CUE:DURATION contains the following:
  + duration – Duration in fractional seconds
  + id – An identifier, unique among all ad avails CUE tags
  + type – SpliceOut
  + time – The PTS time for the ad avail, in fractional seconds

**Example**  
This is the tag for an ad avail lasting 414\.171 PTS:  

```
#EXT-X-CUE:DURATION="201.467",ID="0",TYPE="SpliceOut",TIME="414.171"
```

## Ad Marker: Elemental<a name="sample-manifests-hls-elemental"></a>

**Structure**    
****    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/sample-manifests-hls.html)

**Tag Contents**  
+ CUE\-OUT contains DURATION
+ CUE\-OUT\-CONT contains Elapsed time and Duration
+ CUE\-IN has no content

**Example**  

```
#EXT-X-CUE-OUT:30.000 
.
.
.
# EXT-X-CUE-OUT-CONT: 8.308/30 
.
.
.
# EXT-X-CUE-OUT-CONT: 20.391/30
.
.
.
# EXT-X-CUE-IN
```

## Ad Marker: SCTE\-35 Enhanced<a name="sample-manifests-hls-scte-35-enhanced"></a>

Structure    
****    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/sample-manifests-hls.html)

Tag Contents  
+ OATCLS\-SCTE35 containing the base64 encoded raw bytes of the original SCTE\-35 ad avail message\.
+ ASSET containing the CAID or UPID as specified in the original SCTE35 message\.
+ 1 CUE\-OUT per ad avail\.
+ CUE\-OUT\-CONT containing the following:
  + The elapsed time of the avail\.
  + The duration declared in the original SCTE35 message\.
  + SCTE35 containing the base64 encoded raw bytes of the original SCTE\-35 ad avail message\.

    These lines repeat until the ad avail ends\.
+ CUE\-IN to indicate the end of the avail\.

Example  

```
#EXT-OATCLS-SCTE35:/DA0AAAAAAAAAAAABQb+ADAQ6QAeAhxDVUVJQAAAO3/PAAEUrEoICAAAAAAg+2UBNAAANvrtoQ==  
#EXT-X-ASSET:CAID=0x0000000020FB6501  
#EXT-X-CUE-OUT:201.467
.
.
.
#EXT-X-CUE-OUT-CONT:ElapsedTime=5.939,Duration=201.467,SCTE35=/DA0AAAA+…AAg+2UBNAAANvrtoQ==
.
.
.
#EXT-X-CUE-IN
```
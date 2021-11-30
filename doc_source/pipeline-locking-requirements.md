# Requirements for pipeline locking<a name="pipeline-locking-requirements"></a>

**Channel requirements**

The channel must be a standard channel with only one input attached\. It doesn't work in a channel with multiple inputs where your implement input switching\. 

**Output requirements**

Pipeline locking works only with the following types of output groups:
+ HLS
+ MediaPackage
+ Microsoft Smooth
+ UDP

The channel can contain output groups other than the supported ones\. MediaLive will not perform pipeline locking on those output groups\. This means that there is no guarantee that the two pipelines will be frame\-accurate with each other\. 
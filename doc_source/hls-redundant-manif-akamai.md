# Rules for Akamai CDNs<a name="hls-redundant-manif-akamai"></a>

Read this table if you are setting up redundant manifests with an Akamai CDN\. If your downstream system is not an Akamai CDN, see [Rules for most downstream systems](hls-redundant-manif-most-systems.md)\.


|  Field  |  Rule  | 
| --- | --- | 
|  Protocol/domain/path portion of the two destination URIs \(A and B\)  | Can be different from each other, or can be the same\.  | 
|  BaseFilename portion of the two destination URIs \(A and B\)  |  Can be different from each other, or can be the same\. It *cannot* use [variable identifiers](variable-data-identifiers.md) that include the date or time\. The combination of the protocol/domain/path and the baseFilename must be unique in A and B\. This rule ensures that the output files from the two pipelines don’t overwrite each other\.   | 
|  Name modifier  |  There is only one instance of this field\. Both pipelines use the same value\. It *cannot* use [variable identifiers](variable-data-identifiers.md) that include the date or time\.   | 
|  Segment modifier  |  There is only one instance of this field\. Both pipelines use the same value\.  It *can* use [variable identifiers](variable-data-identifiers.md) that include the date or time\.  | 
| Base URL Manifest A and Base URL Manifest B  |  These fields apply only if you are also implementing [custom manifest paths](hls-manifests-how-work.md#hls-custom-manifest-paths)\. Typically, with Akamai CDNs, you do implement custom manifest paths\. Complete both fields\.  | 
| Base URL Content A and Base URL Content B  |  These fields apply only if you are also implementing [custom manifest paths](hls-manifests-how-work.md#hls-custom-manifest-paths)\.  Complete both fields\.   | 
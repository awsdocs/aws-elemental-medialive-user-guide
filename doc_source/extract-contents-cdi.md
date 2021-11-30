# Identifying content in a CDI source<a name="extract-contents-cdi"></a>

The content in a CDI source always consists of uncompressed video, uncompressed audio, and captions\. 

Obtain identifying information from the content provider:
+ For video – You don't need identifying information\. MediaLive always extracts the first video that it encounters\.
+ For audio – The source might include multiple audio tracks, typically, one for each language\. Obtain the track number of each audio asset to extract\.
+ For captions – The source might contain captions in its ancillary data\. The supported caption types are ARIB, embedded \(EIA\-608 or CEA\-708\), and Teletext \(OP47\):
  + ARIB captions – You don't need any information\. With ARIB captions, MediaLive extracts all the languages\.
  + For embedded captions, obtain the languages in the channel numbers\. For example, "channel 1 is French"\. 
  + For Teletext captions, [if your plan for captions](assess-uss-captions.md) is to convert the captions to a different format, you must obtain the page numbers for the languages that you want to convert\. If you plan to pass through the captions as Teletext in the output, you don't need any identifiers\.
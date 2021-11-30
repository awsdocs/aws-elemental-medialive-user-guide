# How MediaLive constructs these paths<a name="hls-how-construct-custom-paths"></a>

The custom paths to the child manifests are constructed as follows:
+ You complete the **Base URL manifest** fields, or the **Base URL content** fields, or both\. 

  For example:

  ```
  http://198.51.100/sports/viewing/
  ```

  Note the slash at the end of the value\.
+ MediaLive prepends that value to the [default path](hls-manifests-how-work.md#hls-default-manifest-paths)\. For example:

  ```
  http://198.51.100/sports/viewing/curling-high.m3u8
  ```
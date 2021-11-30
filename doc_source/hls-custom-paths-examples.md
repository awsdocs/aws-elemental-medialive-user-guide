# Examples of custom paths<a name="hls-custom-paths-examples"></a>

In all these examples, assume the following:
+ In the main manifest, the default path to the child manifests is this relative path:

  ```
  curling-high.m3u8
  ```
+ In the child manifest, the default path to the media files is this relative path:

  ```
  curling-high-000001.ts
  ```

**Example 1**  
The downstream system is going to move the files from the location where MediaLive pushes them\. The downstream system will move the files in such a way that the child manifests are still in the same relative location to the parent manifests, and the media files are still in the same relative location to the child manifests\.  
Therefore, you don’t need to customize the paths\. The default paths will still work after the move\.

**Example 2**  
You want the main manifest and the child manifests to include absolute paths to their respective files\. You set up as follows:  
+ Complete the **Base URL manifest A** field to specify this absolute path: 

  ```
  http://198.51.100/sports/viewing/
  ```

  Inside the main manifest, the path to the child manifest will now be the following:

  ```
  http://198.51.100/sports/viewing/curling-high.m3u8
  ```
+ Complete the **Base URL content** field to specify this absolute path:

  ```
  http://203.0.113.55/sports/viewing/
  ```

  Inside the child manifests, the paths to the media files will now be the following:

  ```
  http://203.0.113.55/sports/viewing/curling-high-000001.ts
  ```
This example illustrates that the domain for the two sets of files could be different\.

**Example 3**  
You want the parent manifest to include absolute paths to the child manifests\. But you want the child manifests to include paths to the media files that are relative to the child manifest\. In this case, you customize the path to the child manifests, but you continue to use the default paths to the media files\.  
+ You complete the **Base URL manifest A** field to specify this absolute path: 

  Inside the main manifest for pipeline A, the path to the child manifest will now be the following:

  ```
  http://198.51.100/sports/viewing/curling-high.m3u8
  ```
+ You don’t complete the **Base URL content A** field\. 

  Inside the child manifests, the paths to the media files will still be the default:

  ```
  curling-high-000001.ts
  ```
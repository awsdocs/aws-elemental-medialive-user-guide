# Options for handling Microsoft Smooth output<a name="downstream-system-for-mss"></a>

If you are delivering to a Microsoft Smooth Streaming server, the setup depends on whether you want to protect your content with a digital rights management \(DRM\) solution\. DRM prevents unauthorized people from accessing the content\. 
+ If you don't want to implement DRM, then create a Microsoft Smooth output group\. 
+ If you do want to implement DRM, you can create an HLS or MediaPackage output group to send the output to AWS Elemental MediaPackage, then use AWS Elemental MediaPackage to add DRM\. You will then set up AWS Elemental MediaPackage to deliver to the Microsoft Smooth origin server\.
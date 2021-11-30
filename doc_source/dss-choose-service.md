# Choosing among the AWS media services<a name="dss-choose-service"></a>

If your preferred downstream system is another AWS media service, following are some useful tips for choosing the service to use: 
+ If you need to choose between AWS Elemental MediaPackage or AWS Elemental MediaStore for HLS outputs, follow these guidelines: 
  + Decide if you want to protect your content with a digital rights management \(DRM\) solution\. DRM prevents unauthorized people from accessing the content\. 
  + Decide if you want to insert ads in your content\. 

  If you want either or both of these features, you should choose MediaPackage as the origin service because you will need to repackage the output\. 

  If you do not want any of these features, you could choose MediaPackage or AWS Elemental MediaStore\. AWS Elemental MediaStore is generally a simpler solution as an origin service, but it lacks the repackaging features of MediaPackage\. 
+ If you have identified AWS Elemental MediaPackage as an origin service, decide if you will produce the HLS output using an HLS output group or a MediaPackage output group\. For guidelines on making this choice, see the [next section](hls-choosing-hls-vs-emp.md)\.
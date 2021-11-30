# Choosing between the HLS output group and MediaPackage output group<a name="hls-choosing-hls-vs-emp"></a>

If you want to deliver HLS output to AWS Elemental MediaPackage, you must decide if you want to create an HLS output group or a MediaPackage output group\. 

There are differences in the setup that you must follow for each type of output group:
+ Read the information about [channel class](plan-redundancy-mode.md) and decide whether you will create a standard channel or a single\-pipeline channel\. If you decide to create a single\-pipeline channel, then you should create an HLS output group\. 
+ The MediaPackage output requires less setup\. AWS Elemental MediaLive is already set up with most of the information that it needs to package and deliver the output to the AWS Elemental MediaPackage channel that you specify\.
+ For a MediaPackage output, the MediaLive channel and the AWS Elemental MediaPackage channel must be in the same AWS Region\. 
+ In a MediaPackage output, there are some restrictions on setting up ID3 metadata\. For details, see [Working with ID3 metadata](id3-metadata.md)\. 
# Changing pipeline redundancy in an existing channel<a name="pipeline-redundancy-change"></a>

To enable or disable pipeline redundancy on an existing channel, you must update the channel class\.

## Changing the channel class to standard – option A<a name="channel-class-option-a"></a>

You can change a single\-pipeline channel to a standard channel\. Follow this procedure if you originally set up the single\-pipeline channel with [standard\-class inputs and upgrade potential](single-channel-upgrade.md)\. 

Perform these steps:
+ Arrange with your upstream systems to start sending two instances of the source content\.
+ [Stop the channel](starting-stopping-deleting-a-channel.md)\.
+ Change the channel class to standard class\. See the steps after this list\.

  You have now upgraded the channel from a single\-pipeline channel with standard\-class inputs to a standard channel with standard\-class inputs\.
+ [Restart the channel](starting-stopping-deleting-a-channel.md)\.

**To change the channel class**

1. Obtain a second destination address for each output group\. Each address is at the downstream system of each output group\.

   For example, if the channel has an HLS output group \(with an HTTPS server as its downstream system\) and an Archive output group \(with an Amazon S3 bucket as its downstream system\), you must enter the URL to a new destination address at the HTTPS server, and the URL to a new folder in the Amazon S3 bucket\.

   [Plan these destinations](setting-up-downstream-system.md) now, in the same way as you planned the destination addresses when you originally set up the channel\. You might need to contact the owner of each downstream system\.

1. On the **Channels** page, choose the channel\. \(Don't choose the channel name\.\)

1. On the menu, choose **Actions**, **Other channel actions**, **Update channel class to STANDARD**\.

1. In the dialog box, choose **Confirm**\.

1. On the **Update channel class to Standard** page, enter the destination addresses that you identified in step 1\. There is one field for each output group in the channel\.

1. Choose **Submit**\. MediaLive updates the channel and creates a new pipeline called pipeline 1\. The source for this pipeline is the previously dormant URL\. When you start the channel, MediaLive ingests content from that URL, produces output, and sends the output to the new destinations in every output group\. 

## Changing the class—option B<a name="channel-class-option-b"></a>

You can change a single\-pipeline channel to a standard channel\. Follow this procedure if you originally set up a [single\-pipeline channel with single\-class inputs](single-pipeline-no-upgrade.md)\.

Perform these steps:
+ Arrange with your upstream systems to start sending two instances of the source content\.
+ [Stop the channel](starting-stopping-deleting-a-channel.md)\.
+ Detach each single\-class input\. To detach the inputs, you must [edit the channel](editing-deleting-channel.md) and remove the attached inputs\.
+ [Edit each input](edit-input.md) to convert it to standard\-class, and to add a second source\.
+ Edit the channel to change the channel class to standard class\. See the steps after this list\.
+ [Edit the channel](editing-deleting-channel.md) to reattach each input\.

  You have now upgraded the channel from a single\-pipeline channel with single\-class inputs to a standard channel with standard\-class inputs\.
+ [Restart the channel](starting-stopping-deleting-a-channel.md)\.

**To change the channel class**

1. Obtain a second destination address for each output group\. Each address is at the downstream systems of each output group\.

   For example, if the channel has an HLS output group \(with an HTTPS server as its downstream system\) and an archive output group \(with an Amazon S3 bucket as its downstream system\), you must enter the URL to a new destination address at the HTTPS server, and the URL to a new folder in the Amazon S3 bucket\.

   Plan these destinations now, in the same way as you planned the destination addresses when you originally set up the channel\. You might need to contact the owner of each downstream system\.

1. Edit the URLs in every single\-class input to include a second URL, for the second source that will provide content to the newly added pipeline\. 
   + For a push input, [edit the input](edit-input.md) to include an address for the second input source\. Give that address to the owner of the upstream system, so that they can push source content to that address\. You should also find out from the upstream system the address that the new source will be pushed from\. Make sure that this address is covered by the input security group for the channel\. 
   + For a pull input, obtain a new address from the owner of the downstream system\. [Edit the input](edit-input.md) to include that address\. After the second pipeline is created, MediaLive will be able to pull the second source content \(for the second pipeline\)\. 

1. On the **Channels** page, choose the channel\. \(Don't choose the channel name\.\)

1. On the menu, choose **Actions**, **Other channel actions**, **Update channel class to STANDARD**\.

1. In the dialog box, choose **Confirm**\.

1. On the **Update channel class to STANDARD** page, enter the destination addresses that you identified in step 1\. There is one field for each output group in the channel\.

1. Choose **Submit**\. MediaLive updates the channel and creates a new pipeline called pipeline 1\. When you start the channel, MediaLive sends the output from this pipeline to the new destinations in every output group\. 
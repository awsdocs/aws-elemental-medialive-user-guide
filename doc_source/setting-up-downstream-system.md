# Setting Up the Downstream System<a name="setting-up-downstream-system"></a>

 You must set up the device or application that will be downstream of MediaLive\. The downstream system is different for different outputs\.

The output from MediaLive is considered input to this downstream system\. You must set up this downstream input now, because when you create the MediaLive channel you need the location of that input\. 

**Important**  
Typically, you set up the MediaLive as a [standard channel](plan-redundancy-mode.md), so that the channel has two pipelines\. The procedures in this section assume that you have decided to set up in this way\. The procedures therefore describe how to set up the downstream system to expect outputs at two destinations\.   
If you have decided to set up a single\-pipeline channel, then there is only one pipeline in the channel\. Follow these procedures, but set up the downstream system to expect outputs at only one destination\.
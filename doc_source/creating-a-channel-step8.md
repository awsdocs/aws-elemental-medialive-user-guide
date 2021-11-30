# Step 8: Set up the captions encodes<a name="creating-a-channel-step8"></a>

In [Step 5: Create output groups and outputs](creating-a-channel-step4.md), you created the output groups and outputs that you identified when you planned the channel\. Each output section contains a **Stream settings** section\. You must now create all the captions [encodes](channels.md#encode) for the outputs\. 

**General procedure**  
Follow this general procedure to set up the captions encode\.

1. Decide how you're going to create each encode:
   + From scratch\.
   + By sharing an encode that already exists in this output or another output in the channel\.
   + By cloning an encode that already exists in this output or another output in the channel\.

   You might have already made this decision\. If not, you should decide now\. For more information, see [Step 4: Design the encodes](designing-encodes.md)\.

   You can share or clone captions encodes within one output, from one output to another in the same output group, or from one output to an output in another output group\.

1. Read the appropriate sections that follow\.

**Topics**
+ [Creating an captions encode from scratch](#create-captions-scratch)
+ [Creating an captions encode by sharing](#create-captions-share)
+ [Creating a captions encode by cloning](#create-captions-clone)

## Creating an captions encode from scratch<a name="create-captions-scratch"></a>

**To set up the captions encodes from scratch**

1. On the **Create channel** page, find the output group that you [created](creating-a-channel-step4.md)\. 

1. Under that output group, find the output where you want to set up an captions encode\.

1. If you need to add a new captions to this output, choose **Add captions**, then choose **Create a new captions description**,

1. Choose the captions encode, and in **Codec settings**, choose the format to use for this encode\. More fields appear\.

1. In **Captions selector name**, choose the selector that is the source for this captions encode, according to [your plan](channel-map-output-source.md)\. You [created this selector](input-audio-selectors.md) earlier\.

1. Complete other fields as appropriate, to configure the captions encode\. For detailed information about setting up captions encodes, see [Step 4: Create captions encodes](create-captions-encodes.md)\.

## Creating an captions encode by sharing<a name="create-captions-share"></a>

You can create one captions encode and share it among several outputs\. Follow the [earlier procedure](#create-captions-scratch) to create the encode once\. Then set up the encode for the other outputs using the following steps\.

Note that the procedure for sharing an captions encode is nearly identical to the procedure for sharing a video encode or captions encode\.

**To create an captions encode by sharing**

1. On the **Create channel** page, find the output group that you [created](creating-a-channel-step4.md)\. 

1. Under that output group, find the output where you want to set up an captions encode\.

1. The output might contain a captions encode that MediaLive has automatically added\. If you don't plan to use this captions encode, remove it\. Choose the captions encode and choose **Remove captions**\.

1. Create a new captions\. Choose **Add captions**\. A menu appears that includes the option **Use an existing captions description**, followed by a list of the captions that currently exist in the entire channel\. Choose the captions that you want to use\.

1. On the dialog that appears, choose **Share the existing settings**\.

   The fields for this encode appear\. Above the first field is an information message that lists all the outputs that share this encode\. 

   You might want to change the captions description to include the term *shared*, as a reminder to yourself\.

   Keep in mind that there is only one instance of this encode in the channel\. Therefore, if you change a field, you will change the field in all the other outputs that use this encode\. 

   Remember this rule if you change the **Captions selector name** field\. If you specify a different selector in the encode in one output, you change it in all the outputs that share this encode\. If you actually want to specify a different selector, you might need to clone the encode instead of sharing it\.

## Creating a captions encode by cloning<a name="create-captions-clone"></a>

You can create one captions encode and clone it among several outputs\. The *source* encode could be an encode that you created from scratch, or it could be an encode that was itself created by cloning\. For example, create *captions\-1*, then clone it to *captions\-2*, then clone *captions\-2* to *captions\-3*\.

Note that the procedure for cloning an captions encode is nearly identical to the procedure for cloningg a video encode or captions encode\.

**To create an captions encode by cloning**

1. On the **Create channel** page, find the output group that you [created](creating-a-channel-step4.md)\. 

1. Under that output group, find the output where you want to set up an captions encode\.

1. The output might contain a captions encode that MediaLive has automatically added\. If you don't plan to use this captions encode, remove it\. Choose the captions encode and choose **Remove captions**\.

1. Create a new captions\. Choose **Add captions**\. A menu appears that includes the option **Use an existing captions description**, followed by a list of the captions that currently exist in the entire channel\. Choose the captions that you want to use\.

1. Choose the captions encode that you want to use as the source for the new captions encode\.

1. On the dialog that appears, choose **Clone the existing settings**\. The fields for the encode appear, with the fields showing the values from the source encode\.

1. Complete other fields as appropriate, to configure the captions encode\. For detailed information about setting up captions encodes, see [Step 4: Create captions encodes](create-captions-encodes.md)\.

1. Keep in mind that this cloned encode is a new encode instance\. If you change fields, you don't affect the source encode\.
# Setting up a multiplex<a name="setting-up-multiplex"></a>

There are three components involved in an MPTS: a MediaLive multiplex, MediaLive programs, and MediaLive channels \(and their attached MediaLive inputs\)\. You must create these components in this order:
+ Create the MediaLive multiplex\. 
+ Create programs in that multiplex\. A program can't exist on its own; it always exists in a multiplex\. 
+ Create one channel and attach it to the program\. A multiplex channel can't exist on its own; it always exists in a program\.

## Step 1: Plan the availability zones<a name="plan-multiplex-step.title"></a>

Identify two AWS Availability Zones for the multiplex\. AWS Elemental MediaLive runs the pipelines for the multiplex in those two zones\. Follow these guidelines:
+ If the multiplex will include a MediaConnect input and that input already exists, then make a note of the region and Availability Zones of the flows in that input\. In the steps below, you will set up the multiplex to use the same region and Availability Zones\.
+ If the multiplex will include a MediaConnect input and that input doesn't already exists, then decide choose a region and Availability Zones\. The flows and the multiplex must use the same region and Availability Zones\.
+ If the multiplex won't include a MediaConnect input, then choose a region and Availability Zones for the two pipelines in the multiplex\.

## Step 2: Create the multiplex<a name="create-multiplex-step.title"></a>

 Create the multiplex\. Make sure to create the multiplex in the identified region and Availability Zones\. For more information, see [Creating a multiplex and program](multiplex-create.md)\.

## Step 3: Create the inputs<a name="create-multiplex-inputs-step.title"></a>

You must create the inputs for the channels that you will create\. As with any channel, you must create the inputs before you create each channel\. 
+ Follow the regular procedure for [creating the input](create-input.md)\. 
+ Inputs for the channels that are used in a multiplex can be MP4 inputs or MediaConnect inputs\. 
+ For MediaConnect inputs, make sure that you follow these rules:
  + The flows in the MediaConnect inputs must use the region and zones that you identified in step 1\.
  + All the MediaConnect inputs must use these same two zones\.

## Step 4: Create the programs<a name="create-multiplex-programs-step.title"></a>

Create the programs to add to the multiplex\. For more information, see [Creating a multiplex and program](multiplex-create.md)\. You can add up to 20 programs per multiplex\. The multiplex must already exist\.

## Step 5: Create the channels<a name="create-multiplex-channels-step"></a>

Create a channel for each program\. The program must already exist\. 

Using the console, there are two ways to create the channel for a program: 
+ From the **Program** details page\. After you create each program, details about the program appear, including a link to immediately create a channel for the program\. If you choose this link, the **Create channel** page appears, with many fields already set to the value that is applicable to a channel used in a multiplex\. For a summary of the fields that MediaLive sets for you, see [Restrictions](#multiplex-restrictions)\.
+ From the navigation pane\. You can create a channel in the usual way, by choosing **Channel** from the navigation pane\. For information about setting some of the fields, see [Restrictions](#multiplex-restrictions)\. 

For more information about completing the channel fields, see [Creating a channel from scratch](creating-channel-scratch.md)\.

### Restrictions<a name="multiplex-restrictions"></a>

There are some restrictions on the configuration of a channel that is used in a multiplex: 

**Restrictions in the Output Group **

The channel can contain only one output group, of type **Multiplex**\. This type follows the rules of a UDP output group\. It can contain only one output\. 

**Restrictions in the Output**

The following restrictions apply to the output fields\.


****  

| Field |  Value | 
| --- | --- | 
| In Multiplex destination, the Multiplex program field | From the list, choose the multiplex program that this channel belongs to\. | 
| In Stream settings, for Video | The output can contain one, and only one, video asset\. | 
| In Stream settings, for Audio | The output can contain zero or more audio assets\. | 
| In Stream settings, for Captions | The output can contain zero or more captions assets\. | 

**Restrictions in the Video**

The following rules apply to the fields in the video\.


****  

| Field |  Value | 
| --- | --- | 
| Width and Height \(resolution\) | Set values for both the width and height\. The width can be up to1920 pixels\. The height can be up to1080\. | 
| Codec settings | Choose H\.264 \(AVC\) or H\.265 \(HEVC\)\. | 
| In Aspect Ratio, the PAR control field | Set a value\. This is required\. Don't set up to follow the aspect ratio from the source\. | 
| In Rate control, the Rate control mode field | Choose Multiplex\. | 
| In Rate control, the Buffer size field | Keep blank\. | 
| In Frame rate, the Framerate field |  Set a value\. This is required\. Don't set up to follow the frame rate from the source\.  The numerator and denominator must result in a decimal value in this range: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/setting-up-multiplex.html)  | 
| In GOP structure |  For **GOP size units**, choose **FRAMES**\. Then set **GOP structure** to 6 or greater\. Or for **GOP size units**, choose **SECONDS**\. Then set **GOP structure** to 0\.1 or greater\.  | 
| In Codec details, the Profile field |  If the codec is H\.264, choose one of these profiles: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/setting-up-multiplex.html) If the codec is H\.265, choose one of these profiles: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/setting-up-multiplex.html)  | 

**Features That Are Not Restricted**

There are some features of the channel that you can set up in the same way as you would set them up in a regular channel: 
+ For video configuration fields not mentioned in the table earlier in this section, you can set the field to suit your workflow\.
+ For audio, you can set up as you would set up in a UDP output group in a regular channel\.
+ For captions, you can set up as you would set up in a UDP output group in a regular channel\. Specifically, make sure that the input captions and output captions follow the rules for a UDP output group\. See [Reference: supported captions](supported-captions.md)\.
+ For other features, if the feature is available for a UDP output group, then it is available for a channel in a multiplex\.
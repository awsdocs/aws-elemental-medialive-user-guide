# Creating a multiplex and program<a name="multiplex-create"></a>

A MediaLive multiplex provides configuration information for an MPTS, including the bitrate of the entire MPTS\. 

You can create a multiplex from scratch, or you can clone an existing multiplex\. Cloning a multiplex is similar to cloning a channel—the values in most of the fields are copied to the new multiplex\. 

You can create a program inside a multiplex\. You can't create a program without attaching it to a multiplex\.

**To create a multiplex**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Multiplexes**\. 

1. On the **Multiplexes** page, choose **Create**\. 

1. Complete the fields on the **Create multiplex** page\. 

1. Choose **Create**\. 

   The multiplex is added to the **Multiplexes** page\. After the status of the multiplex changes to IDLE, your next step is to add programs to the multiplex\. For more information, see later in this section\. 

**To create a multiplex by cloning**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Multiplexes**, and then choose the multiplex that you want to clone\. 

1. On the **Details** pane, choose **Multiplex actions**, and then choose **Clone**\. 

**To create a program**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Multiplexes**, and then choose the multiplex where you want to add the program\. 

1. On the **Details** pane, choose the **Programs** tab\. 

1. Choose **Create program**\. 

1. Complete the fields on the **Create program** page\. 

1. Choose **Create**\. 

   The **Program** details pane appears for this program\. Note that the channel state always specifies CHANNEL MISSING\. 

1. Either now or later, you must create a channel for this program: 
   + You can choose **Create channel** to immediately add a channel to this program\. 
   + You can add a channel later, in the same way that you create a channel that isn't part of a multiplex\.

The channel attached to a program is a regular channel in which the output group is always a multiplex output group\. 

For information about special steps for completing the fields in a channel in a multiplex, see [Step 5: Create the channels](setting-up-multiplex.md#create-multiplex-channels-step)\. 
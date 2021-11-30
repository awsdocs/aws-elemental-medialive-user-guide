# Font styles for Burn\-in or DVB\-Sub<a name="font-styles-for-burn-in"></a>

If the output captions are Burn\-in or DVB\-Sub, you can specify the look of the captions\.

If you are using the same captions source in several outputs and all those outputs use the same format, then you must set up the font style information identically in each output\. If you don't, you get an error when you save the channel\. For example, you have an Archive output that includes DVB\-Sub captions converted from captions selector "embedded"\. And you have a UDP output that also includes DVB\-Sub captions converted from the same captions selector\. You must set up the font style information separately—in the Archive output, and then in the UDP output\. But you must enter the same information in both outputs\. 

For example, output A might use **Captions Selector 1** with the **Destination Type** set to **Burn\-in**\. And output B might also use **Captions Selector 1** with the **Destination Type** set to **Burn\-in**\. You set the font information once in output 1 and again in output 2\. But you must set up all the font information identically in both outputs\.
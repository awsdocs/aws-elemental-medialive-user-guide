# Step 7: Set up the schedule with input switches<a name="ips-set-up-schedule"></a>

After you create the inputs and the channel \(step 6\), you must create actions in the schedule to set up the input switches that you want\. For detailed information about creating input switch actions, see [Creating actions in the schedule \(console\)](schedule-using-console-create.md)\. 

Follow these guidelines when setting up the schedule:
+ You should create at least some of the fixed input switches and follow input switch actions before you start the channel\. 
+ The first input switch in a new channel should be an immediate input switch\. You should create this input switch before you start the channel\. Setting up in this way ensures that the order of ingest of inputs is always being controlled by the schedule\.
+ For other immediate switches, you might be able to add the switches to the schedule before you start the channel\. Or you might be able to add them only after the channel is running\. You should have an idea of which of these strategies applies to your plan\.
+ Plan to update the schedule regularly\. Remember that you can add actions to the schedule without stopping the channel\.
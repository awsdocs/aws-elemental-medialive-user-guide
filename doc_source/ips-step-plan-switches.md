# Step 5: Plan the input switches in the schedule<a name="ips-step-plan-switches"></a>

After you design the selectors for each input \(step 4\), you must plan the order that you want MediaLive to follow when it ingests these inputs\.

**Result of This Step**

By following this step, you have identified one input as being the first that you will add to the channel\. 

You have also identified an ordered list of input switches\. You have the following for each switch:
+ An action name for the switch\. 
+ The name of the input attachment associated with the switch\.
+ The switch input identified as either static or dynamic\.
+ The type of switch—fixed, follow, or immediate\.

**Topics**
+ [Plan the action names](ips-plan-action-names.md)
+ [Plan the order of input switches](ips-order-switches.md)
+ [Example of a list of input switches](#ips-ordered-list-examples)
+ [Handling the transition when the next input is fixed or immediate](ips-transition-gap.md)
+ [Handling the transition when the next input is follow](transition-follow-success.md)
+ [**Prepare input—reducing latency when the next input is immediate**](#ips-plan-immediate-prepare-input)

## Example of a list of input switches<a name="ips-ordered-list-examples"></a>

This example shows a list of planned input switches\. The first input is an immediate switch to a file input\. Then there are several short file inputs that are follow switches, so that the switch occurs at the end of the previous input\. These inputs run one after another, but the plan is to interrupt these at any time with an immediate switch to the first live input\. After that, the schedule switches back and forth between two live inputs\. You don't know the exact timing for the switches, so you will set up these switches as immediate switches\. 

Ordered list: action name, start type, input attachment name
+ startup, immediate, banner
+ static\-1, follow, short\-clip\-12
+ static\-2, follow, short\-clip\-32
+ static\-3, follow, short\-clip\-77
+ static\-4, follow, short\-clip\-18

Immediate switches to occur at any time:
+ static\-live\-studio, immediate, live\-1
+ static\-live\-alternate, immediate, live\-2

## **Prepare input—reducing latency when the next input is immediate**<a name="ips-plan-immediate-prepare-input"></a>

You might have an input switch that you have identified as an immediate input switch, but you don't know when the switch will need to occur\. You only know that you will be given just a few seconds advance notice\. In this situation, you might want to prepare the input in advance by creating a prepare input action\. For more information, see [Preparing inputs in AWS Elemental MediaLive](feature-prepare-input.md)\.
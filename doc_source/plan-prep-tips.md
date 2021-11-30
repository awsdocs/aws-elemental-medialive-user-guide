# Guidelines for choosing the start type<a name="plan-prep-tips"></a>

Following are some guidelines for deciding which start type to use with an input prepare, depending on the scenario\. 

Keep in mind that you can only prepare one switch at a time\. When a prepare action starts, MediaLive starts preparing the input, and automatically stops any other active prepare input action\. 

Therefore, the guiding principle is to make sure that you don't start preparing input X and accidentally *stop *preparing input Y, if input Y needs to be prepared before input X\. 

**Topics**
+ [Scenario A](#plan-prep-tips-scenario-A)
+ [Scenario B](#plan-prep-tips-scenario-B)
+ [Scenario C](#plan-prep-tips-scenario-C)
+ [Scenario D](#plan-prep-tips-scenario-D)

## Scenario A<a name="plan-prep-tips-scenario-A"></a>

You are flipping between two inputs\. The switch start is always undetermined, so that each switch is an immediate switch\. There might be more switches interspersed among these switches, but they don't need preparing\.

```
Switch to input A (immediate)
Switch to input B (immediate)
Switch to input A (immediate)
Switch to input B (immediate)
```

The easiest plan is to start preparing B after each switch to A, and to start preparing A after each switch to B\. You could set up each prepare input action with any of these start types:
+ Fixed\. The start time for prepare B is some time after the start time for switch A\.
+ Immediate\. Recommended\. You could add the prepare B action at the same time as the immediate A switch, or shortly afterward\.
+ Follow \(start\)\. You should add the prepare B action and the immediate A switch in the same [batch update command](about-batch-update-schedule.md)\. The reference action for the prepare B action is input A\.
+ Follow \(end\)\. You can add the prepare B action at any time after switch A has been added to the schedule\. The reference action for the prepare B action is input A\.

For example:

```
Switch to input A (immediate)
Prepare input B (immediate)
Switch to input B (immediate)
Prepare input A (immediate)
Switch to input A (immediate)
Prepare input B (immediate)
Switch to input B (immediate)
```

## Scenario B<a name="plan-prep-tips-scenario-B"></a>

There is an immediate switch to A, then there are several fixed or follow switches\. You anticipate that the next immediate switch will be to A again\. 

```
Switch to input A (immediate)
Switch to input C (fixed or follow)
Switch to input D (fixed or follow)
Switch to input A (immediate)
```

After the switch to A, MediaLive continues preparing A\. Therefore, there is no need to prepare it again\. Furthermore, if input A is the only input that ever has an immediate switch, you can prepare A once, before the first time that you switch to it\. You don't need to prepare it again\.

## Scenario C<a name="plan-prep-tips-scenario-C"></a>

There is an immediate switch to A, then there are several fixed or follow switches\. You anticipate that the next immediate switch will be to B\. 

```
Switch to input A (immediate)
Switch to input C (fixed or follow)
Switch to input D (fixed or follow)
Switch to input B (immediate)
```

You know that the next immediate switch will be to input B, so you can start preparing it anytime after the switch to input A\. You could set up each prepare input action with any of these start types:
+ Fixed\. The start time for prepare B is at least 10 seconds before the start of switch B\.
+ Immediate\. Recommended\. You could add the prepare B action at the same time as the immediate A switch, or shortly afterward\.
+ Follow \(start\)\. Not recommended\. You could, for example, set up the prepare B action to follow the start of switch C or the start of switch D\.
+ Follow \(end\)\. Not recommended\. You could, for example, set up the prepare B action to follow the end of switch A or the end of switch C\. Don't set it up to follow the end of switch D\.

For example:

```
Switch to input A (immediate)
Prepare input B (immediate)
Switch to input C (fixed or follow)
Switch to input D (fixed or follow)
Switch to input B (immediate)
```

## Scenario D<a name="plan-prep-tips-scenario-D"></a>

There is an immediate switch to input B, then there are several fixed or follow switches\. You anticipate that there will be another immediate switch but initially you don't know if it will be to input B or input E\. 

```
Switch to input A (immediate)
Switch to input C (fixed or follow)
Switch to input D (fixed or follow)
Switch to input B or E (immediate)
```

When you know which input you will switch to, you can start preparing it\. When you want to prepare it, the current input could be A, C, or D\. You could set up each prepare input action with any of these start types:
+ Fixed\. The start time for prepare B \(or E\) is at least 10 seconds before the start of switch B \(or E\)\.
+ Immediate\. Recommended\. Add the prepare input action as soon as you know whether the switch will be to B or E\.
+ Follow \(start\)\. Not recommended\. You could, for example, set up the prepare B \(or E\) action to follow the start of switch C or the start of switch D\.
+ Follow \(end\)\. Not recommended\. You could, for example, set up the prepare B \(or E\) action to follow the end of switch A or the end of switch C\. Don't set it up to follow the end of switch D\.

For example:

```
Switch to input A (immediate)
Switch to input C (fixed or follow)
Switch to input D (fixed or follow)
Prepare input E (immediate)
Switch to input E (immediate)
```
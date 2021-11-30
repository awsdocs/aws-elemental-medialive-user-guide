# Partner CDI inputs<a name="feature-cdi-partner"></a>

A partner CDI input is a specific configuration of a CDI input\. You must set up two CDI inputs as partners if you want to support automatic input failover for a CDI source\. The two inputs always work together, as the two inputs in an [automatic failover](automatic-input-failover.md) pair\. The two inputs can be used only together, as a failover pair\.

**Topics**
+ [Regular inputs versus partner inputs](#cdi-input-partner-vs-regular)
+ [Rules for using partner CDI inputs](#cdi-input-partner-rules)
+ [Creating the set of partner inputs](#cdi-input-create)
+ [Editing the set of partner inputs](#cdi-input-edit)
+ [Deleting partner inputs](#cdi-input-delete)

## Regular inputs versus partner inputs<a name="cdi-input-partner-vs-regular"></a>

When you create a CDI input, you must decide whether you need to create a *regular* CDI input or a set of *partner* CDI inputs\. This decision depends on how you want to implement pipeline redundancy and automatic input failover\.

The following table describes the type of input to create depending on the workflow\.


****  
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/medialive/latest/ug/feature-cdi-partner.html)

## Rules for using partner CDI inputs<a name="cdi-input-partner-rules"></a>

These rules apply to partner inputs:
+ Automatic failover – You can only use the partner inputs as a failover pair\. 
+ Input switching – You can't use the partner inputs in an input switching workflow, where sometimes you switch to one partner and at other times you switch to the other partner\. 
+ Single channel – You can use the partner inputs only in one channel\. You can't attach one partner to one channel, and the other partner to a different channel\.

## Creating the set of partner inputs<a name="cdi-input-create"></a>

To create the partner inputs, you must follow a special procedure\. See [Creating a partner CDI push input in Amazon VPC](input-create-cdi-partners.md)\. 

## Editing the set of partner inputs<a name="cdi-input-edit"></a>

You can edit the inputs in the same way as you update regular CDI inputs\. See [Editing an input](edit-input.md)\.

## Deleting partner inputs<a name="cdi-input-delete"></a>

The two inputs have equal standing\. The first input that you create when you follow the special procedure isn't the owner input or principal input\. Therefore, these rules apply when you [delete](delete-input.md) a partner input:
+ You can delete one input without deleting the other\. 

  If you do so, the remaining input simply becomes a regular CDI input\. If you delete the first input, the name of the second input doesn't automatically change\. For example, if the input had the name myInput \- partner, it will still have the name myInput \- partner, even though it is no longer a partner CDI input\. You can edit the input to change the name\.
+ You can delete the second input, then create the partner input again, from the first input\. The IP addresses of the new input will be assigned the port 5001\.
+ You can delete the first input, then create the partner input again, from the second input\. The IP addresses of the new input will be assigned the port 5000\. 

  If you didn't change the name of the second input \(the default has the suffix, for example, **myInput \- partner**\), then the new input has the name **myInput \- partner \- partner**\. You can edit the input to change the name\.
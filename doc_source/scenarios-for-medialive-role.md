# Options for Implementing the Role<a name="scenarios-for-medialive-role"></a>

There are two options for setting up the trusted entity role in AWS Elemental MediaLive: a simple option and a complex option\. 

## Simple Option<a name="about-simple-scenario"></a>

The simple option typically applies when users in your organization are using AWS Elemental MediaLive to encode the organization's own assets \(not assets belonging to customers\), and you don't have rigorous rules about accessing assets \(for example, you don't have video assets that can be handled only by specific users or departments\)\. 

With the simple option, there is only one role: `MediaLiveAccessRole`\. All channels use this role and all users can attach that role to the channels that they work with\. 

The simple option works only on the MediaLive console\. It can't be performed using the AWS CLI, for example\. 

The `MediaLiveAccessRole` role grants broad access to operations and complete access to all resources\. It allows either read\-only access or read/write access to all the services that MediaLive must access when a channel is running\. And most significantly, it allows full access to all the resources associated with those services\. 

If the simple option is suitable to your deployment, see [Requirements for Permissions for the Simple Option](set-up-simple-scenario.md)\.

## Complex Option<a name="about-complex-scenarios"></a>

The complex option applies when the `MediaLiveAccessRole` role is too broad for your use, given that it allows broad access to operations and complete access to all resources\. 

For example, you might have the following requirements:
+ A requirement that a given channel should be allowed to access only specific resources and another channel should be allowed to access only specific, different resources\. Therefore, you need to create several access roles, each of which narrows down permissions to a different set of resources\.
+ A requirement that each user should be allowed to display only specific roles on the console, to prevent a user from viewing a role they should not know about or to prevent a user from selecting the wrong role\.

If the complex option is applicable to your deployment, see [Setting Up AWS Elemental MediaLive as a Trusted Service](setup-medialive-trusted-service.md)\.
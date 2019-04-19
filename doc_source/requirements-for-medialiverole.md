# Requirements for AWS Identity and Access Management—Trusted Entity Role<a name="requirements-for-medialiverole"></a>

This requirements analysis must be performed by a person in your organization who understands your organization's requirements for access to resources\. This person must understand whether there is a requirement that AWS Elemental MediaLive channels should be restricted in their access to resources in other AWS services\. For example, this person should determine whether channels should be restricted in their access to containers in AWS Elemental MediaStore so that a specified channel can access some containers and not others\.

Every time a user creates a channel, they must attach an IAM role that sets up MediaLive as a trusted entity for that channel\. The user makes this attachment using the **IAM role** pane on the **Create channel** page on the MediaLive console\. 

You must decide what access you need to give to users for working in this **IAM role** pane\. 

If you followed the procedures in [Creating a Non\-Administrator IAM User](preproduction-set-up-users.md) to set up users for the period when you are experimenting with MediaLive, then you already set up this trusted entity role\. You set it up by creating the `MediaLiveAccessRole` role\. However, you should still read this section to determine if `MediaLiveAccessRole` is suitable for your organization when you are working in a production environment\.

**Topics**
+ [About the Trusted Entity Role](about-trusted-entity.md)
+ [Options for Implementing the Role](scenarios-for-medialive-role.md)
+ [Requirements for Permissions for the Simple Option](set-up-simple-scenario.md)
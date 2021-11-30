# Setting up AWS Elemental MediaLive as a trusted service<a name="setup-medialive-trusted-service"></a>

You need to read this section only if you determined in [Options for implementing the role](scenarios-for-medialive-role.md) that the simple option for setting up the trusted entity role does not work for your deployment\.

This section describes how to implement the complex option\. It provides the following information:
+ Background information about how the trusted entity role is created and used in the complex option\. 
+ Instructions for identifying the trusted entity role or roles that your deployment needs and creating these roles\.
+ Instructions for granting limited permissions to regular users so that they can use only specific trusted entity roles\. 

If you are not familiar with the purpose of the trusted entity role, first read [About the trusted entity role](about-trusted-entity.md) and [Options for implementing the role](scenarios-for-medialive-role.md)\.

**Topics**
+ [How the trusted entity is created and attached](complex-scenario-how-entity-handled.md)
+ [Creating trusted entity roles](complex-scenario-create-trusted-entity-role.md)
+ [Setting up permissions for non\-administrator users](complex-scenario-user-permissions.md)
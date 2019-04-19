# Setting up AWS Elemental MediaLive as a Trusted Service<a name="preproduction-trusted-entity"></a>

Every time a user creates a channel, they must attach an IAM role that sets up MediaLive as a trusted entity for that channel\. You must give the user the permissions to set up this trusted entity\.

You give this permission when you create the user\. You create a policy called **MediaLiveTrustedEntityAccess** and attach it to the group that the users belong to\. For detailed information, see [Step 1: Create Customer Managed Policies](setup-user-step-policies.md)\.
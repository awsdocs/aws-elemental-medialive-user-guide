# Deleting a MediaLive device<a name="device-delete"></a>

You don't delete MediaLive devices\. Instead, if the upstream system deregisters the AWS Elemental Link hardware, the MediaLive device no longer appears in the **Devices** section\. Note that this is the only way that the MediaLive device is removed\. 
+ If someone powers down the hardware device, the MediaLive device still appears in the list\.
+ If the AWS Elemental Link hardware is disconnected from the internet or the connection from MediaLive to the AWS Elemental Link hardware is down, the MediaLive device still appears in the list\.
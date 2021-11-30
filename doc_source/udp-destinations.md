# Fields for the output destination<a name="udp-destinations"></a>

The following fields configure the destination of the output:
+ **Output group** – **UDP destination** sections
+ **Output** – **Output settings** – **Network settings** – **Buffer msec**

**To specify the destination for the output**

1. When you [discussed your requirements](origin-server-rtmp.md) with the operator who manages the downstream system that will receive UDP content, you should have obtained the following information:
   + The URLs
   + The port numbers

   For example:

   `udp://203.0.113.28:5000`

   `udp://203.0.113.33:5005`

1. Enter the URLs, including the port number, in one or both of the **URL** fields in the **UDP destinations** section\. 

1. If you [enable FEC](udp-container.md), leave space between the port numbers for the two destinations\. 

   For example, if one destination is **rtp://203\.0\.113\.28:5000**, assume that FEC also uses port 5002 and 5004\. So the lowest possible port number for the other destination is 5005: **rtp://203\.0\.113\.33:5005**\.

1. \(Optional\) In the **Output** section, complete the **Buffer msec** field as appropriate\. For details, choose the **Info** link next to the field in the MediaLive console\.
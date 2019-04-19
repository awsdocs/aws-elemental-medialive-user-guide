# Enabling Decoration – Microsoft Smooth<a name="procedure-to-enable-decoration-ms-smooth"></a>

With Microsoft Smooth, if you enable manifest decoration, instructions are inserted in the sparse track\.

Manifest decoration is enabled at the output group level, which means that the sparse tracks for all outputs in that group will include instructions based on the SCTE\-35 content\.

**To enable decoration**

1. In the channel that you are creating, make sure that you have set the ad avail mode\. See [Getting Ready: Set the Ad Avail Mode](getting-ready-set-the-ad-avail-mode.md)\.

1. In the navigation pane, find the desired Microsoft Smooth output group\. 

1. For **Sparse track**, for **Sparse track type**, choose **SCTE\_35**\. 

1. Complete **Acquisition point ID**, only if encryption is enabled on the output\. Enter the address of the certificate\. 
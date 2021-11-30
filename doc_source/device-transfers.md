# Transferring a device<a name="device-transfers"></a>

The owner of a device can initiate an outgoing transfer to a different AWS account, to transfer ownership of the device to that account\. The recipient of a transfer can accept or reject the incoming transfer\.

**Topics**
+ [Initiating a device transfer](#device-transfer-send)
+ [Cancelling an outgoing device transfer](#device-transfer-cancel)
+ [Accepting a device transfer](#device-transfer-receive)

## Initiating a device transfer<a name="device-transfer-send"></a>

You can transfer a device to a different AWS account\.

**To transfer a device to another AWS account**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Devices**\.

1. In **Input devices**, go to the card for the MediaLive device that you want to transfer and choose the link\.

1. On the details page for the device, choose **Transfer device**\.

1. On the **Transfer input device** dialog box, enter the AWS account to transfer to, and type an optional message\. 

1. Choose **Transfer**\.

1. In the navigation pane, choose **Devices**, then choose **Device transfers**\. The transfer request appears in the **Outgoing transfers** tab\. 

   The transfer is pending until the recipient accepts the device\. While the transfer is pending, you can cancel the request, as described in the following section\.

   If the recipient accepts the transfer, the device no longer appears in any of your device lists\.

   If the recipient rejects the transfer, the device appears again on your **Input devices** page\.

## Cancelling an outgoing device transfer<a name="device-transfer-cancel"></a>

You can cancel a device transfer while the request is pending\.

**To cancel an outgoing device transfer**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Devices**\.

1. In **Input devices**, choose **Device transfers**, then choose the **Outgoing transfers** tab\.

1. In the list of transfers, choose the transfer you want to cancel, then choose **Cancel**\.

## Accepting a device transfer<a name="device-transfer-receive"></a>

The owner of a device can transfer a device to your AWS account\. For example, a distributor of AWS Elemental Link might sell you a device, then transfer the device to your account\. Or someone in your organization might transfer the device from one AWS account in your organization to another AWS account\.

If you are expecting to receive a device transfer, you should regularly check the **Incoming transfers** tab on the **Device transfers** page\. You must accept the transfer\. You can't use the device until you have accepted the transfer\.

**To accept a device transfer**

1. Open the MediaLive console at [https://console\.aws\.amazon\.com/medialive/](https://console.aws.amazon.com/medialive/)\.

1. In the navigation pane, choose **Devices**\.

1. In **Input devices**, choose **Device transfers**, then choose the **Incoming transfers** tab\.

1. In the list of transfers, choose the device that you want to accept, then choose **Accept** or **Reject**\.

1. In the navigation pane, choose **Devices** again\. The device now appears in the list of devices on the **Input devices** page\.
# Summary of actions<a name="multiplex-create-delete-edit-summary"></a>

The following table summarizes the create, edit, and delete capabilities for the multiplex, program, and channel\.


****  

| Item | Action | Note | 
| --- | --- | --- | 
| Multiplex | Create |  | 
|  | Edit |  The multiplex can be idle or running\. The channels can be all idle, or all running, or a combination or idle and running\. Exception: To change the **Max Video Buffer Delay** field, the multiplex must be idle\.  | 
|  | Delete | The multiplex must be idle, and must not have any associated programs\. | 
| Program | Create | The multiplex for the program can be idle or running\.  | 
|  | Edit | The multiplex for this program can be idle or running\. The channel for this program can be idle or running\. | 
|  | Delete | The multiplex for this program can be idle or running\. The program can't have any associated channel\. | 
| Channel | Create | The multiplex for this channel can be idle or running\. The program for the channel must be empty\. | 
|  | Edit | The channel must be idle\. The multiplex for this channel can be idle or running\.  | 
|  | Delete | The channel must be idle\. The channel can still be attached to a program\. | 
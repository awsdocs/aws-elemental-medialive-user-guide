# Requirements for AWS Elemental MediaPackage<a name="requirements-for-mediapackage"></a>

Your deployment might send outputs to AWS Elemental MediaPackage, either by creating an [HLS output group or by creating a MediaPackage output group](hls-choosing-hls-vs-emp.md)\. \(Note that both MediaLive and MediaPackage have "channels"; however, they are different objects\.\)

The user needs permissions to perform actions in MediaPackage when they use the MediaLive console and when they use the MediaLive workflow wizard\. 


| Permissions | Service name in IAM | Actions | 
| --- | --- | --- | 
| On the MediaLive console, view the MediaPackage channels in the dropdown list on the MediaLive channel\. | MediaPackage | Describe\* | 
| Use the workflow wizard to create a MediaPackage channel, if your organization supports MediaPackage as an output destination\.Use the workflow wizard to delete a workflow that includes a MediaPackage output\. | MediaPackage | List\*`Describe*``Create*``Delete*` | 
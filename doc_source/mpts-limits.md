# Restrictions for multiplexes<a name="mpts-limits"></a>

Following is a summary of the restrictions associated with multiplexes:
+ There are service quotas for the number of multiplexes you can create\. For more information, see [Quotas in AWS Elemental MediaLive ](limits.md)\.
+ These limitations apply to a multiplex:
  + Each multiplex produces only one MPTS\. The MPTS has two pipelines, so it is sent to two destinations\. 
  + All multiplex outputs must include video\. 
+ These limitations apply to a program:
  + Each program in a multiplex is single use\. It is attached only to one multiplex, and you can use it only for that multiplex\.
+ These limitations apply to a channel in a multiplex:
  + Each channel is single use\. You can attach it to only one program in the multiplex, and you can use it only for that multiplex\. 
  + Each channel contains one and only one output group, of type multiplex\. It can't contain any other type of output group\.
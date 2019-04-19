# Scope of Processing by Feature<a name="scope-by-feature"></a>

The SCTE\-35 features have different scopes in terms of the output groups and outputs that they affect:

**Blackout or ad avail blanking**

Blackout applies at the *global output* level\. All the relevant content in every output in every output group is blanked\. 

Ad avail blanking also applies at the *global output* level\. All the ad avails in every output in every output group are blanked\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/scte35_scope_blanking.png)

**Decoration **

Manifest decoration applies at the *output group* level\. All the outputs in that output group have their manifests decorated\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/scte35_scope_manifest.png)

**SCTE\-35 passthrough or removal**

SCTE\-35 passthrough or removal applies at the *output* level\. The messages are passed through or removed only in a specific output\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/medialive/latest/ug/images/scte35_scope_passthrough.png)
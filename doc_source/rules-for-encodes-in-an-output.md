# Rules for Encodes in an Output<a name="rules-for-encodes-in-an-output"></a>

The following rules apply to the organization of encodes into outputs:
+ **Video** – Each video encode goes in its own output\. One output can't contain two videos\. 
+ **Audio** – In a non\-ABR asset, each audio encode goes in its own output\. In an ABR asset, the audio encodes don't go in their own output; they are contained in the same output as the video encode\.
+ **Captions** – Embedded\-type captions encodes always go in the same output as the video encode, inside \(embedded\) in the video encode\. Object\-style captions encodes go in their own object in the same output as the video encode\. Sidecar captions encodes always go in their own output\. 

These rules mean that one output can contain the following:
+ A video encode
+ A video encode and one or more audio encodes
+ A video encode and one embedded\-type captions
+ A video encode and one or more object\-type captions
+ A video encode, one or more audio encodes, and one embedded\-type captions
+ A video encode, one or more audio encodes, and one or more object\-type captions
+ An audio encode
+ A sidecar\-type captions
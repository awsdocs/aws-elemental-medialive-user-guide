# AWS Elemental MediaLive Terminology<a name="what-is-terminology"></a>

CDN  
A content distribution network \(CDN\) is a network of servers that is downstream of the origin server or packager\. The CDN distributes the content from the origin server to dozens or hundreds of networked servers that serve the content to your viewing users\. This distributed network ensures that content can be delivered to thousands or millions of viewing users simultaneously\.

Channel   
A MediaLive channel ingests and transcodes \(decodes and encodes\) source content from the inputs that are attached to that channel, and packages the new content into outputs\. 

Channel class  
Each channel belongs to one of the following classes:   
+ Standard class – a channel has two processing pipelines
+ Single\-pipeline class – a channel has one processing pipeline

Channel configuration  
A MediaLive channel configuration contains information about how the channel ingests, transcodes, and packages content into output\. 

Downstream system   
The *downstream system* is a set of one or more servers that is positioned after MediaLive in the workflow\. The downstream system handles the content that is output from MediaLive\.

Encode  
An encode exists within an output\. There are three types of encodes: video, audio, and captions\. Each encode contains the instructions for one video stream, one audio stream, or one captions track that the transcoding process will create\. Different encodes have different characteristics\. For example, one video encode produced from the input might be high resolution while another is low resolution\. 

Input  
A MediaLive input holds information that describes how the upstream system and the MediaLive channel are connected\. The input identifies endpoints \(IP addresses\) in MediaLive \(for a push input, where the upstream system pushes to MediaLive\) or source IP addresses on the upstream system \(for a pull input, where MediaLive pulls from the upstream system\)\. MediaLive has different input types for different formats and protocols of the source content\. For example, HLS input and RTMP Push input\.

Input security group  
A MediaLive input security group is a set of one or more ranges of IP addresses that define an allow list\. You associate one or more input security groups with a push input in order to identify a range of IP addresses that are allowed to push content to the input\. 

Output  
An output exists within an output group\. It is a collection of encodes that you want to handle as one set\.

Origin service  
An origin service might be part of the downstream system that is positioned after MediaLive in the workflow\. It accepts the video output from MediaLive\. 

Output Group  
An output group is a collection of outputs within the MediaLive channel\. 

Packager  
A packager might be part of the downstream system\. It accepts the video output from MediaLive and repackages it\. AWS Elemental MediaPackage is a packager\. 

Pipeline  
In MediaLive, there are one or two separate and independent pipelines that perform the processing within the MediaLive input and the MediaLive channel\.

Playback device  
A playback device is the final component of the downstream system\. It is the device that the people who are your audience use to view the video\.

Schedule  
Each MediaLive channel has an associated schedule\. The schedule contains a list of actions to perform in the channel at a specific time\.

Source content  
The video content that MediaLive transcodes\. The content typically consists of video, audio, captions, and metadata\. 

Upstream system  
The system that is in front of MediaLive in the workflow and that holds the source content\. Examples of an upstream system are a streaming camera or appliance that is directly connected to the internet, or a contribution encoder that is located in a stadium at a sports event\. 
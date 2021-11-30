# Working with MediaLive multiplexes<a name="eml-multiplex"></a>

A MediaLive multiplex creates a multi\-program transport stream \(MPTS\)\. You might be interested in creating a MediaLive multiplex if you are a service provider who has experience with distributing transport stream \(TS\) content over RTP or UDP\. 

To set up a multiplex, you create a MediaLive multiplex\. You then add MediaLive programs to the multiplex\. Finally, you create one MediaLive channel for each program, and associate each channel with its program\. 

For conceptual information about setting up a multiplex, see [Multiplex and MPTS in AWS Elemental MediaLive](feature-multiplex.md)\. 

**Topics**
+ [Summary of actions](multiplex-create-delete-edit-summary.md)
+ [Creating a multiplex and program](multiplex-create.md)
+ [Creating a channel](multiplex-channel-create.md)
+ [Editing multiplexes, programs, and channels](edit-multiplex-program-channel.md)
+ [Deleting multiplexes, programs, and channels](delete-multiplex-program.md)
# Static inputs and dynamic inputs<a name="how-dynamic-inputs-work"></a>

A file input in a multiple\-input channel can be set up as a *static input* or a *dynamic input* \(A live input is always a static input\)\. The following examples use MP4 files, but note that both MP4 and Transport Stream \(TS\) files are supported\.
+ With a static input, the source content of the input is always the same file\. For example, `s3ssl://DOC-EXAMPLE-BUCKET/my-movie.mp4`\.
+ With a dynamic input, all or part of the source content of the input is a variable\. For example, `s3ssl://DOC-EXAMPLE-BUCKET/movies/$urlPath$`\. Each time you set up to switch to this input, you replace the variable with a different file\. For example, `s3ssl://DOC-EXAMPLE-BUCKET/movies/my-movie.mp4` in one input switch and `s3ssl://DOC-EXAMPLE-BUCKET/movies/mlaw.mp4` in another input switch\.

Using dynamic inputs lets you increase the number of video sources that you can use in the channel, while still observing the limit on the number of inputs that you can attach to the channel\. 

To set up a dynamic input, you create the input with a variable as all or part of the URL of the file\. Then, in the schedule, when you create an input switch that uses that input, you replace the variable with a real filename\. 

The [procedure for setting up](ips-step-design-inputs.md) for input switching, later in this section, provides detailed information about deciding whether you should set up some inputs as dynamic inputs\.
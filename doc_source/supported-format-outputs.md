# Format support by output container<a name="supported-format-outputs"></a>

There are several factors that control your ability to include captions of a specific format in your outputs:
+ **The type of input container** – A given input container can contain captions in some formats and not in others\.
+ **The format of the input captions** – A given format of captions can be converted to some formats and not to others\.
+ **The type of output containers** – A given output container supports some captions formats and not others\. 

For example, assume that your input container is an MP4 container and your output is HLS, and that you want to include WebVTT captions in the HLS output\. You can implement this use case only if the MP4 container holds 608 embedded captions\. You can't implement it if, for example, the MP4 container holds Ancillary captions\. 

For more information about all the supported combinations of input container, input format, and output container, see [Reference: supported captions](supported-captions.md)\.
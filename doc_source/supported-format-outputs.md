# Format Support by Output Container<a name="supported-format-outputs"></a>

There are several factors that control your ability to include captions of a specific format in your outputs:
+ **The type of input container** – A given input container can contain captions in some formats and not in others\.
+ **The format of the input captions** – A given format of captions can be converted to some formats and not to others\.
+ **The type of output containers** – A given output container supports some captions formats and not others\. 

For example, if your input container is an MP4 container and your output is HLS, and you want to include Web\-VTT captions in the HLS output, you can do so if the MP4 container holds 608 embedded captions\. But you can't include Web\-VTT captions if the MP4 container holds Ancillary captions\. 

For more information about all the supported combinations of input container, input format, and output container, see [Reference: Supported Captions](supported-captions.md)\.
# Planning the captions selectors<a name="ips-plan-captions-sels"></a>

When you set up the captions selectors for an input, you specify both the format and the language to extract from the input\. Each input has the number of selectors that is appropriate to the captions formats in that input\. Therefore, each input might contain a different number of selectors\. The method for extracting captions is different from the method for extracting audio\. 

## Rule 1: Plan the number of selectors for an input that is appropriate to the input and output<a name="ips-captions-sels-rule-a"></a>

In each input, you must create the number of selectors that is appropriate to the input format and output format:
+ For example, if you want to extract embedded in order to pass through the captions, you create one selector\.
+ If you want to extract embedded in order to convert them to TTML, you create one selector for each language\.

After you have identified all the selectors for all the inputs, you might end up with a list like this: 
+ Selector for embedded passthrough – applies to input 1, input 3, and input 4
+ Selector for embedded, English – applies to input 1, input 3, and input 4
+ Selector for embedded, French – applies to input 1, input 3, and input 4
+ Selector for DVB Sub, English – applies to input 2
+ Selector for DVB Sub, French – applies to input 2
+ Selector for Teletext passthrough – applies to all inputs

Note that inputs 1, 3, and 4 each contain four selectors\. Input 2 contains three selectors\. 

## Rule 2: Plan the same selector names in every input<a name="ips-captions-sels-rule-b"></a>

Every unique selector must have the same selector name across all the inputs\. This rule exists because each output references the selectors only once\. The output doesn't reference the selector once for each different input where the selector exists\.

We recommend that you give each selector a name that includes the language and the source format\. Descriptive names help you to choose the correct selector on the output side\. 
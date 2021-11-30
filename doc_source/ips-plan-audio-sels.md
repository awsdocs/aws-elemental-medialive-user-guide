# Plan the audio selectors<a name="ips-plan-audio-sels"></a>

There are several rules you must follow when planning the audio selectors\. When you set up the audio selectors for an input, you specify the language to extract but you don't specify the format of the audio in that input\. AWS Elemental MediaLive extracts that input so it can be included in the output\. The output expects to be able to find the specific extracted language\. 

## Rule 1: Plan the same number of selectors in every input<a name="ips-audio-sels-rule-a"></a>

The selectors in each input must extract sufficient assets to produce every output audio encode\. In addition, every input must have the same number of selectors\.

For example, assume you have an output that requires AAC 2\.0 audio in English and French\. You have a second output that requires Dolby 5\.1 audio in English and French\. You have a third output that requires Dolby 5\.1 audio in French, Spanish, and Portuguese:
+ If the first input contains Dolby Digital 5\.1 in the four languages, you must create four selectors—one for each language\. The audio extracted by these four selectors can produce all the languages\. It can produce Dolby Digital 5\.1 for the first output, and it can produce AAC 2\.0 for the second because you can set up that output for remixing\.

  Although the channel has seven output audio encodes, you don't need seven selectors\.
+ If the second input contains Dolby Digital 5\.1 in French \(but no other language\), and also contains AAC 2\.0 in English, Spanish, and Portuguese \(but not in French\), you create four selectors\. The selector for French will find that audio only in the Dolby Digital 5\.1\. The selectors for the other languages will find those audio assets only in the AAC 2\.0\.
+ If the third input contains Dolby Digital 5\.1 in the four languages, and also contains AAC 2\.0 in the four languages, you still create only four selectors\.

  Although you might think to create selectors to extract the AAC 2\.0 audio for French and English just for this input, you mustn't do this because the first input doesn't have these selectors\. Remember that every input must have the same number of selectors\.

## Rule 2: Plan a separate selector for Dolby Digital Plus 7\.1<a name="ips-audio-sels-rule-b"></a>

If the channel includes at least one output with Dolby Digital Plus 7\.1, create one selector in every input for that audio asset\. On the output side, in every audio encode for Dolby Digital Plus 7\.1, you will map the audio encode to that selector\.

After you have identified all the selectors for all the inputs, you might end up with a list like this: 
+ Selector for English
+ Selector for French
+ Selector for Spanish
+ Selector for Portuguese
+ Selector for EAC3 passthrough \(EAC3 is another name for Dolby Digital Plus\)

Each of these selectors applies to all inputs, regardless of the audio format in that input\. 

## Rule 3: Plan the same selector names in every input<a name="ips-audio-sels-rule-c"></a>

Every selector for a specific language must have the same name across all the inputs\. This rule exists because each output references the selectors only once\. The output doesn't reference the selector once for each different input\.

We recommend that you give the selectors names that include the language\. Don't include the format unless you create a selector for Dolby Digital Plus 7\.1\. 
# Step 1: Create Caption Selectors in the Input<a name="identify-captions-in-the-input"></a>

You must identify the captions that you want to use and assign each to a caption selector\. If you don't create any caption selectors, you will not be able to include captions in the output\. All the captions will be removed from the media\.

**Identify the Captions You Want**

1. Identify which captions are in the input \(the provider of the input should provide you with this information\) and identify which captions are available to you as external files\. Identify the caption formats and, for each format, the languages\. 

1. Identify which of those formats and languages that you want to use\.

1. Determine how many caption selectors to create in the input in the channel, using the following guidance: 

   + For embedded\-to\-embedded, create a single caption selector for all languages\. All languages are passed through; there is no other option\. For details, see [[ERROR] BAD/MISSING LINK TEXT](embedded.md)\.

   + For teletext\-to\-teletext, create a single caption selector for all languages \(in fact, one caption selector for the entire content\)\. All languages are passed through; there is no other option\. For details, see [[ERROR] BAD/MISSING LINK TEXT](teletext.md)\.

   + In all other cases, create one caption selector for each language and format combination\.

You end up with a list of caption selectors to create\. For example:

+ Caption Selector 1: Teletext captions in Czech

+ Caption Selector 2: Teletext captions in Polish

**Create Caption Selectors**

In AWS Elemental MediaLive, extract the desired captions by adding a caption selector in the channel\. Each extracted caption is contained in one caption selector\.

1. In the channel that you are creating, in the navigation pane, choose **Channel and input details**\.

1. For **Input settings**, choose **Add caption selectors**\.

1. For **Caption selector name**, type a suitable name\. For example, TTML Czech\. 

1. For **Selector settings**, choose the format of the source captions\. 

1. For most formats, more fields appear\. For details about a field, choose the Info link next to the field\. In addition, see extra information on DVB\-Sub or SCTE\-27, on Embedded, or on Teletext\.

1. Create more caption selectors, as required\. 
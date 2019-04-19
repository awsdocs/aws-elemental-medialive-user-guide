# Channel Input—HLS Pull Input<a name="input-hls-pull"></a>

To verify that the input is set up correctly, look at the **Input sources** section\. It shows the locations of the source video\. You specified these locations when you created the input:
+ If the channel is set up as a standard channel, you specified two locations\.
+ If the channel is set up as a single\-pipeline channel, you specified one\.

For example, for an HTTPS pull:

**https://203\.0\.113\.13/newschannel/anytownusa\.m3u8** and **https://203\.0\.113\.54/newschannel/anytownusa\.m3u8** 

Or, for an AWS Elemental MediaStore pull:

**mediastoressl://eri39n\.data\.mediastore\.us\-west\-2\.amazonaws\.com/premium/canada/mlaw\.m3u8** and **mediastoressl://eri39n\.data\.mediastore\.us\-west\-2\.amazonaws\.com/redundant/premium/canada/mlaw\.m3u8** 
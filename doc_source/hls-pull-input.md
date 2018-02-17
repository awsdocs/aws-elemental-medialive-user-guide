# Creating an HLS Pull Input<a name="hls-pull-input"></a>

1. Open the AWS Elemental MediaLive console at https://console\.aws\.amazon\.com/medialive?region="region"\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. In the **Input details** section, for **Input** name, type a name\.

1. For **Input type**, choose **HLS**\. 

1. In the **Input sources **section, type the full URI of the two locations where AWS Elemental MediaLive will pull the M3U8 manifest source from\. Obtain these locations from the upstream system\. Enter the location of the M3U8 manifest in one of these formats:

   + For a location that supports HTTP or HTTPS, type an HTTP or HTTPS URI\. For example, `https://203.0.113.0/newschannel/anytownusa.m3u8` and `https://203.0.113.254/newschannel/anytownusa.m3u8`\.

   + For a manifest that is stored on AWS Elemental MediaStore, the URI must include the data endpoint for the container\. For example, the M3U8 file is called mlaw\.m3u8 and it is stored on the container "movies" in the folder path "premium/canada"\. The URL for the container might be **eri39n\.data\.mediastore\.us\-west\-2\.amazonaws\.com**\. The value you enter in this field would be **mediastoressl://eri39n\.data\.mediastore\.us\-west\-2\.amazonaws\.com/premium/canada/mlaw\.m3u8**\. 

   + For a manifest that is stored on Amazon S3, type the protocol as **s3** or **s3ssl**, and then type the bucket and object for the manifest\. For example, `s3:/movies/mlaw.m3u8` and `s3:/movies/redundant/mlaw.m3u8`\. 

1. If you are using a secure connection \(S3SSL\), you must also enter the user name and EC2 password key for accessing the location\. These credentials are stored on the Amazon EC2 Systems Manager Parameter Store\. For more information, see [[ERROR] BAD/MISSING LINK TEXT](about-EC2Password.md)\.

1. Choose **Create**\.

1. AWS Elemental MediaLive adds the input to the list of inputs\. The sources don't appear in the list, but if you choose the **Name** link, the details page shows these sources\.
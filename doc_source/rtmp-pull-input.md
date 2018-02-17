# Creating an RTMP Pull Input<a name="rtmp-pull-input"></a>

1. Open the AWS Elemental MediaLive console at https://console\.aws\.amazon\.com/medialive?region="region"\.

1. In the navigation pane, choose **Inputs**\.

1. On the **Inputs** page, choose **Create input**\.

1. In the **Input details** section, for **Input** name, type a name\.

1. For **Input type**, choose **RTMP \(pull\)**\. 

1. In the **Input sources** section, type the full URI of the two locations where AWS Elemental MediaLive will pull the source from\. Obtain these locations from the upstream system\. For example, `rtmp://203.0.113.0:1935/movies/classic` and `rtmp://203.0.113.254:1935/movies/classic`\.

   Also, enter the user name and Amazon EC2 password key for accessing the RTMP location\. These credentials are stored on the Amazon EC2 Systems Manager Parameter Store\. For more information, see [[ERROR] BAD/MISSING LINK TEXT](about-EC2Password.md)\.

1. Choose **Create**\.

1. AWS Elemental MediaLive adds the input to the list of inputs\. The sources don't appear in the list, but if you choose the **Name** link, the details page shows these sources\.
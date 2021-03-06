# Get Information About Multiple On\-Premises Instances<a name="on-premises-instances-operations-view-details-multiple"></a>

You can get information about on\-premises instances by following the instructions in [View Deployment Details with AWS CodeDeploy](deployments-view-details.md)\. You can use the AWS CLI or the AWS CodeDeploy console to get more information about on\-premises instances\.

**To get information about multiple on\-premises instances \(CLI\)**

1. For a list of on\-premises instance names, call the [list\-on\-premises\-instances](http://docs.aws.amazon.com/cli/latest/reference/deploy/list-on-premises-instances.html) command, specifying:
   + Whether to get information about all registered or deregistered on\-premises instances \(with the `--registration-status` option and `Registered` or `Deregistered`, respectively\)\. If you omit this, then both registered and deregistered on\-premises instance names are returned\.
   + Whether to get information only about on\-premises instances tagged with specific on\-premises instance tags \(with the `--tag-filters` option\)\. For each on\-premises instance tag, specify the `Key`, `Value`, and `Type` \(which should always be `KEY_AND_VALUE`\)\. Separate multiple on\-premises instance tags with spaces between each `Key`, `Value`, and `Type` triplet\.

   For example:

   ```
   aws deploy list-on-premises-instances --registration-status Registered --tag-filters Key=Name,Value=CodeDeployDemo-OnPrem,Type=KEY_AND_VALUE Key=Name,Value=CodeDeployDemo-OnPrem-Beta,Type=KEY_AND_VALUE
   ```

1. For more detailed information, call the [batch\-get\-on\-premises\-instances](http://docs.aws.amazon.com/cli/latest/reference/deploy/batch-get-on-premises-instances.html) command, with the names of the on\-premises instances \(with the `--instance-names` option\): 

   ```
   aws deploy batch-get-on-premises-instances --instance-names AssetTag12010298EX AssetTag09920444EX
   ```

**To get information about multiple on\-premises instances \(console\)**

1. Sign in to the AWS Management Console and open the AWS CodeDeploy console at [https://console\.aws\.amazon\.com/codedeploy](https://console.aws.amazon.com/codedeploy)\.
**Note**  
Sign in with the same account or IAM user information you used in [Getting Started with AWS CodeDeploy](getting-started-codedeploy.md)\.

1. From the AWS CodeDeploy menu, choose **On\-premises instances**\. Information about the on\-premises instances is displayed\.
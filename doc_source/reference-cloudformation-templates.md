# AWS CloudFormation Templates for AWS CodeDeploy Reference<a name="reference-cloudformation-templates"></a>

In addition to the other methods available to you in AWS CodeDeploy, you can use AWS CloudFormation templates to perform the following tasks:
+ Create applications\.
+ Create deployment groups and specify a target revision\.
+ Create deployment configurations\.
+ Create Amazon EC2 instances\.

AWS CloudFormation is a service that helps you model and set up your AWS resources using templates\. An AWS CloudFormation template is a text file whose format complies with the JSON standard\. You create a template that describes all of the AWS resources you want, and AWS CloudFormation takes care of provisioning and configuring those resources for you\.

For more information, see [What Is AWS CloudFormation?](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html) and [Working with AWS CloudFormation Templates](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-guide.html) in *AWS CloudFormation User Guide*\. 

If you plan to use AWS CloudFormation templates that are compatible with AWS CodeDeploy in your organization, as an administrator, you must grant access to AWS CloudFormation and to the AWS services and actions on which AWS CloudFormation depends\. To grant permissions to create applications, deployment groups, and deployment configurations, attach the following policy to the IAM users who will work with AWS CloudFormation: 

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [                
        "cloudformation:*"        
      ],
      "Resource": "*"
    }
  ]
}
```

For more information about managed policies, see the following topics:
+ To view the policy that must be attached to IAM users who will create Amazon EC2 instances, see [Create an Amazon EC2 Instance for AWS CodeDeploy \(AWS CloudFormation Template\)](instances-ec2-create-cloudformation-template.md)\.
+ For information about attaching policies to IAM users, see [Working with Managed Policies](http://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-using.html) in *IAM User Guide*\. 
+ To learn how to restrict users to a limited set of AWS CodeDeploy actions and resources, see [AWS Managed \(Predefined\) Policies for AWS CodeDeploy](auth-and-access-control-iam-identity-based-access-control.md#managed-policies)\.

The following table shows the actions an AWS CloudFormation template can perform on your behalf and includes links to more information about the AWS resource types and their property types you can add to an AWS CloudFormation template\. 


| Action |  AWS CloudFormation Resource Type | 
| --- | --- | 
| Create an AWS CodeDeploy application\.  | [AWS::CodeDeploy::Application](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-codedeploy-application.html) | 
| Create and specify the details for a deployment group to be used to deploy your application revisions\. ¹ | [AWS::CodeDeploy::DeploymentGroup](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-codedeploy-deploymentgroup.html) | 
| Create a set of deployment rules, deployment success conditions, and deployment failure conditions that AWS CodeDeploy will use during a deployment\. | [AWS::CodeDeploy::DeploymentConfig](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-codedeploy-deploymentconfig.html) | 
| Create an Amazon EC2 instance\. ² | [AWS::EC2::Instance](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-ec2-instance.html) | 
| ¹ If you specify the version of the application revision that you want to be deployed as part of the deployment group, your target revision will be deployed as soon as the provisioning process is complete\. For more information about template configuration, see [AWS CodeDeploy DeploymentGroup Deployment Revision S3Location](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-codedeploy-deploymentgroup-deployment-revision-s3location.html) and [AWS CodeDeploy DeploymentGroup Deployment Revision GitHubLocation](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-codedeploy-deploymentgroup-deployment-revision-githublocation.html) in the *AWS CloudFormation User Guide*\. ² We provide templates you can use to create Amazon EC2 instances in the regions in which AWS CodeDeploy is supported\. For more information about using these templates, see [Create an Amazon EC2 Instance for AWS CodeDeploy \(AWS CloudFormation Template\)](instances-ec2-create-cloudformation-template.md)\.   | 
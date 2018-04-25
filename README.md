# cloudformation

## Cloudformation template for ASG(MultiAZ)+ELB+AWS_launch_configuration(with_userdata)

AWS CloudFormation Template AutoScalingMultiAZWithNotifications:
  Create a multi-az, load balanced and Auto Scaled sample web site running on an Apache
  Web Server. The application is configured to span all Availability Zones in the
  region and is Auto-Scaled based on the CPU utilization of the web servers. The instances are
  load balanced with a simple health check against the default web page. **WARNING**
  This template creates one or more Amazon EC2 instances and an Elastic Load Balancer.
  You will be billed for the AWS resources used if you create a stack from this template.'

#### How to use

First of all you must specify vars for you template, just create file key.json and fill next filds


	[
	  {
    	"ParameterKey": "KeyName",
    	"ParameterValue": "My"
	  },
	  {
    	"ParameterKey": "InstanceType",
    	"ParameterValue": "t2.micro"
	  },
	  {
    	"ParameterKey": "SSHLocation",
    	"ParameterValue": "0.0.0.0/0"    
	  }
      {
    	"ParameterKey": "VpcId",
    	"ParameterValue": "vpc-fb8e0292"    
	  }
	]
To run this template from CLI you can use next command:

	aws cloudformation create-stack --stack-name MyStackName --template-body file://./main.yaml --parameters file://./key.json

If you want load template from S3 just replace --template-body with --template-url <value>

	--template-url https://s3.eu-central-1.amazonaws.com/cf-templates-1x1h9zg1jiakl-eu-central-1/2018115uJh-main.yaml

## Additional Resources
In the *AWS CloudFormation User Guide*, you can view more information about the following topics:

- Learn how to use templates to create AWS CloudFormation stacks using the [AWS Management Console](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-console-create-stack.html) or [AWS Command Line Interface (AWS CLI)](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-cli-creating-stack.html).
- To view all the supported AWS resources and their properties, see the [Template Reference](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-reference.html).
# DevDays Ansible Compliance Session
This repository has the code related to the Session "Enabling Cloud Native Compliance Using Ansible"
This repo includes EC2 Image Builder, Systems Manager and cloudformation resources.



# Continious Compliance for ec2
Architecture presented in the session covering the lifecycle of compliance for ec2
![](architecture.png)

## EC2 Image Builder

### Ansbile Component Configuration
Below is the Ansible Component you need to build your reciepe
[ec2Image Builder - Ansible Component](/imagebuilder/ec2-ansiblecomponent.yml)

Note: make sure you replace the **bucketname** and **prefix** with your bucket and prefix details

### S3 Bucket
The context of the s3 bucket that contaiuns your ansible playbooks are available here [s3 bucket playbooks](/s3bucket/ec2)


## CloudFormation Template
[ec2Image Builder - Pipeline](/cloudformation/ec2imagebuilderpipeline.yaml)

Use this CFN templace to build an EC2 Image Builder Pipeline based on an Ansible Component

[![Deploy Continious Compliance for ec2 with CloudFormation](images/deploy-to-aws.png)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=EngagementMeter&templateURL=https://solution-builders-us-east-1.s3.us-east-1.amazonaws.com/amazon-rekognition-engagement-meter/latest/main.template)|

**Note**: Ensure you have your playbooks uploaded to an [s3 bucket](/s3bucket/ec2) pre launching the CFN template. This template will only build the pipleline but will not run it

## Systems Manager - State Manager

Zip file for the Ansible Playbook Association

[State Manager - Association](/statemanager/automation.zip)

# Continious Compliance for container images
Architecture presented in the session covering the lifecycle of compliance for ec2
![](architecture-container.png)

## EC2 Image Builder

### Ansbile Component Configuration
Below is the Ansible Component you need to build your reciepe
[ec2Image Builder - Ansible Component](/imagebuilder/container-ansible-component.yaml)

Note: make sure you replace the **bucketname** and **prefix** with your bucket and prefix details

### S3 Bucket
The context of the s3 bucket that contaiuns your ansible playbooks are available here [s3 bucket playbooks](/s3bucket/container)


## CloudFormation Template
[ec2Image Builder - Pipeline](/cloudformation/ansible-container.yaml)

Use this CFN templace to build an EC2 Image Builder Pipeline based on an Ansible Component

**Note**: Ensure you have your playbooks uploaded to an [s3 bucket](/s3bucket/container) pre launching the CFN template. This template will only build the pipleline but will not run it

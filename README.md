# AWS Lambda automated EC2 Management

This project contains an AWS Lambda function that creates a Linux EC2 instance and terminates it after 10 minutes. The Lambda function is triggered via an HTTP API created using API Gateway. The project includes a CloudFormation template to set up the necessary resources.

## Features

- **Automated EC2 Management**: Automatically create and terminate EC2 instances.
- **HTTP API Integration**: Trigger the Lambda function using an HTTP API.
- **Time Savings**: Automate tedious tasks to save developer time.

## Architecture

1. **Lambda Function**: Creates an EC2 instance and schedules its termination.
2. **Lambda Function2**: This one is invoked to delete the ec2 instance after 10 minutes.
3. **API Gateway**: Provides an HTTP endpoint to trigger the Lambda function.
4. **CloudFormation Template**: Sets up the Lambda function, API Gateway, and necessary IAM roles.

## Prerequisites

- AWS Account
- AWS CLI configured with appropriate permissions
- S3 bucket to store the Lambda function code i.e. (lambda_code.zip and terminate_instance.zip)

## Setup

### 1. Upload Lambda Function Code to S3

1. Create a zip file containing your Lambda function code.
2. Upload the zip file to an S3 bucket.

### 2. Deploy CloudFormation Stack

1. Save the CloudFormation template to a file, e.g., `template.yaml`.
2. Use the AWS CLI to deploy the CloudFormation stack:

   ```sh
   aws cloudformation create-stack --stack-name MyLambdaHttpApiStack --template-body file://template.yaml --capabilities CAPABILITY_NAMED_IAM

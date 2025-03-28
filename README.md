# The CDK TypeScript project of couchbase-eks

This project is to test the integration between Couchbase Server and AWS EKS. It uses AWS CDK v2 to manage the CloudFormation stack in AWS.

## Setup The Project With AWS CDK

Here are the commands to setup the project with AWS CDK v2:

```bash
# To install TypeScript.
npm install -g typescript

# To install/upgrade AWS CDK.
npm install -g aws-cdk
cdk --version # To check the version of AWS CDK.

# To bootstrap the environment.
cdk bootstrap
```

## Manage The CloudFormation Stack Using AWS CDK

```bash
export AWS_PROFILE=default       # Replace with your AWS profile.
export AWS_ACCOUNT_ID=1234567890 # Replace with your AWS account ID.
export AWS_REGION=us-east-1      # Replace with your AWS region.

export AWS_STACK_PREFIX=test- # Set the stack prefix to avoid conflicts with other stacks. Default is `test-`.
```

### Stack "vpc"

```bash
cdk synth test-vpc
cdk synth test-vpc > ./test-vpc.yaml
cdk diff  test-vpc

cdk deploy --require-approval never test-vpc

# Use the destroy command only when needed.
# cdk destroy test-vpc
# cdk destroy test-vpc --force
```

### Stack "eks"

```bash
cdk synth test-eks
cdk synth test-eks > ./test-eks.yaml
cdk diff  test-eks

cdk deploy --require-approval never test-eks

# Use the destroy command only when needed.
# cdk destroy test-eks
# cdk destroy test-eks --force
```

### Stack "debug"

```bash
cdk synth test-debug
cdk synth test-debug > ./test-debug.yaml
cdk diff  test-debug

cdk deploy --require-approval never test-debug

# Use the destroy command only when needed.
# cdk destroy test-debug
# cdk destroy test-debug --force
```

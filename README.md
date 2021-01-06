# lambda-recursive-s3-demo 
Recursive AWS Lambda function for processing large S3 file
#### Requirements
* AWS CLI
* AWS account
* Serverless Framework

#### Instructions
* Clone the repo and install the dependencies with `npm i`
* Configure your aws profile with the aws account credentials you want to use for the deployment
```bash
export AWS_DEFAULT_PROFILE=<your aws profile>
export AWS_PROFILE=$AWS_DEFAULT_PROFILE
export AWS_REGION=<your aws region>
```
`TIP` You can check your current credentials with `aws configure list`
* Change the bucket name in serverless.yml inside `provider > iamRoleStatements` and `functions > batch-processor > events > s3 > bucket`, as the name should be unique in the AWS region. 
* Deploy with
```bash
sls deploy
```
* Upload file `expensive_task.json` to the bucket to trigger the lambda
```bash
aws s3 cp expensive_tasks.json s3://<your bucket>/expensive_tasks.json
```


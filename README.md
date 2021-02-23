# aws-cloudformation-stack

aws cloudformation stack for my home studies

## Validate

 aws cloudformation validate-template --template-body file://infrastructure.yml --profil anteverse
{
    "Parameters": [],
    "Description": "AWS CloudFormation VPC Template"
}

## Creation

aws cloudformation create-stack \                                                              ✔ 
--stack-name anteverse \
--template-body file://init.yml \
--parameters ParameterKey=S3BucketUrl,ParameterValue=https://anteverse-stack.s3.amazonaws.com \
  ParameterKey=MyEMailAddress,ParameterValue=youremailexample.com\
  ParameterKey=MyPublicIP,ParameterValue=1.2.3.4  \
--capabilities CAPABILITY_NAMED_IAM \
--profil default
{
    "StackId": "arn:aws:cloudformation:eu-west-3:590095079366:stack/anteverse/6f9da270-7613-11eb-8858-065c9f0d2482"
}

## Update

aws cloudformation update-stack \                                                              ✔ 
--stack-name anteverse \
--template-body file://init.yml \
--parameters ParameterKey=S3BucketUrl,ParameterValue=https://anteverse-stack.s3.amazonaws.com \
  ParameterKey=MyEMailAddress,ParameterValue=youremailexample.com \
  ParameterKey=MyPublicIP,ParameterValue=1.2.3.4 \
--capabilities CAPABILITY_NAMED_IAM \
--profil default
{
    "StackId": "arn:aws:cloudformation:eu-west-3:590095079366:stack/anteverse/6f9da270-7613-11eb-8858-065c9f0d2482"
}

## Delete

aws cloudformation delete-stack --stack-name anteverse --profil anteverse

## Monitor progress

aws cloudformation wait stack-create-complete --stack-name Anteverse --profil anteverse

## Show outputs

aws cloudformation describe-stacks  --profil anteverse                                                                                                                  {
    "Stacks": [
        {
            "StackId": "arn:aws:cloudformation:eu-west-3:666:stack/Anteverse/c1d25870-4c73-11eb-b58b-06ca742260fc",
            "StackName": "Anteverse",
            "Description": "AWS CloudFormation VPC Template",
            "CreationTime": "2021-01-01T20:56:02.227Z",
            "RollbackConfiguration": {},
            "StackStatus": "CREATE_COMPLETE",
            "DisableRollback": false,
            "NotificationARNs": [],
            "Tags": [],
            "DriftInformation": {
                "StackDriftStatus": "NOT_CHECKED"
            }
        }
    ]
}

## Lists stack

aws cloudformation list-stacks --profil anteverse
{
    "StackSummaries": [
        {
            "StackId": "arn:aws:cloudformation:eu-west-3:666:stack/Anteverse/dfc1b570-4ec5-11eb-8982-06db2b17a9ea",
            "StackName": "Anteverse",
            "TemplateDescription": "AWS CloudFormation VPC Template",
            "CreationTime": "2021-01-04T19:48:53.623Z",
            "LastUpdatedTime": "2021-01-04T20:14:31.410Z",
            "StackStatus": "UPDATE_ROLLBACK_COMPLETE",
            "DriftInformation": {
                "StackDriftStatus": "NOT_CHECKED"
            }
        },
        ....
}

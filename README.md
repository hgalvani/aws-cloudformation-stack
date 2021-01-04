# aws-cloudformation-stack
aws cloudformation stack

# Validate
 aws cloudformation validate-template --template-body file://infrastructure.yml --profil anteverse
{
    "Parameters": [],
    "Description": "AWS CloudFormation VPC Template"
}

# Creation 
aws cloudformation create-stack --stack-name Anteverse --template-body file://infrastructure.yml --profil anteverse
{
    "StackId": "arn:aws:cloudformation:eu-west-3:666:stack/Anteverse/dfb07dc0-4c5c-11eb-a31f-0a881ea86c00"
}

# Update
aws cloudformation update-stack --stack-name Anteverse --template-body file://infrastructure.yml --profil anteverse                                                     
{
    "StackId": "arn:aws:cloudformation:eu-west-3:666:stack/Anteverse/c1d25870-4c73-11eb-b58b-06ca742260fc"
}

# Delete
aws cloudformation delete-stack --stack-name Anteverse --profil anteverse

# Monitor progress
aws cloudformation wait stack-create-complete --stack-name Anteverse --profil anteverse


# Show outputs
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

# Lists stack
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

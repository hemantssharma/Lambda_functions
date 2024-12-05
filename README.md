# Lambda_functions
Click on create Lambda function. Provide name, Select python version, select role and Create lambda function.
Deploy code in code section.
Come in configuration section.
Edit configuration details as per requirement.
Edit **environmental variable**.
Add trigger.


# Environment variable: <same for AMI deregister & snapshot_deletion>
Key                Value
BUCKET_NAME      hemantksharma
DIFF_TIME        1
Region_Name      us-east-1
SNS_TOPIC_ARN    arn:aws:sns:us-east-1:767397915550:snapshot_deletion


# Environment variable: <For EBS_vol_deletion-parent_function>
Key                        Value
INVOKE_LAMBDA_ARN       arn:aws:lambda:us-east-1:767397915550:function:Unattached-EBS-Deletion-Child-Function
Region_Name             -
SNS_TOPIC_ARN           -
THRESHOLD_DAYS          -


# Environment variable: <For EBS_vol_deletion-child_function>
Key                        Value
BUCKET_NAME                -
Region_Name                -
SNS_TOPIC_ARN              -
THRESHOLD_DAYS             -

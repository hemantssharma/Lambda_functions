# EBS Volume Cleanup Lambda Function

This AWS Lambda function identifies and deletes unattached EBS volumes that are older than a specified number of days. It also sends notifications via SNS and logs the details to an S3 bucket.

## Prerequisites

- AWS account with necessary permissions
- AWS CLI configured
- Python 3.8 or later
- Boto3 library

## Environment Variables

Set the following environment variables in your Lambda function configuration:

- `Region_Name`: AWS region where your resources are located (e.g., `us-west-2`)
- `SNS_TOPIC_ARN`: ARN of the SNS topic for notifications
- `THRESHOLD_DAYS`: Number of days to check for unattached volumes
- `BUCKET_NAME`: Name of the S3 bucket to store volume details

## Deployment


1. **Update the Lambda function code:**

    - Modify the `lambda_handler` function in `lambda_function.py` as needed.
    - Ensure the environment variables are set correctly.

2. **Deploy the Lambda function:**
```
Click on "Deploy" to upload the code.
```

3. **Set up CloudWatch Events:**

    - Create Event bridge rule to trigger the Lambda function periodically (e.g., monthly).

## Usage

The Lambda function will:

1. Identify unattached EBS volumes older than the specified number of days.
2. Delete the identified volumes.
3. Send a notification via SNS with the details of the deleted volumes.
4. Log the details to an S3 bucket.

## Error Handling

If an error occurs during execution, the function will send an SNS notification with the error details.

## Author
```
Hemant Sharma
```

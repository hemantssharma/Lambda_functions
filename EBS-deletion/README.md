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


**Functionality**
```
1. Send SNS Notification: Sends an SNS notification with a subject and message.
2. Lambda Handler: Main function that:
Deletes ebs volumes older than the specified number of days.
Skips snapshots taken by AWS Backup or tagged as 'Delete == No'.
Logs the details of deleted ebs volumes to an S3 bucket.
Sends SNS notifications for errors and successful deletions.
```

**Deployment**

##### 1. Create Lambda Function:

Go to the AWS Lambda console.
Create a new Lambda function.
Set the runtime to Python 3.x.
Copy and paste the code into the Lambda function editor.

##### 2. Set Environment Variables:

In the Lambda function configuration, set the environment variables as described above.

##### 3. Add Permissions:

Ensure the Lambda function has the necessary permissions to access EC2, SNS, and S3.

##### 4. Test the Function:

Create a test event in the Lambda console and invoke the function to ensure it works as expected.


## Error Handling

If an error occurs during execution, the function will send an SNS notification with the error details.

## Author
```
Hemant Sharma
```

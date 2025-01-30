# AWS Lambda Function for Snapshot Deletion
This AWS Lambda function deletes EC2 snapshots that are older than a specified number of days. It also sends notifications via SNS and logs the details of deleted snapshots to an S3 bucket.

**Prerequisites**
```
AWS account with necessary permissions for EC2, SNS, and S3.
AWS CLI configured with appropriate credentials.
Environment variables set up in the Lambda function configuration.
```
**Environment Variables**
```
Region_Name: AWS region where the resources are located.
SNS_TOPIC_ARN: ARN of the SNS topic for sending notifications.
DIFF_TIME: Number of days to retain snapshots (default is 30 days).
BUCKET_NAME: Name of the S3 bucket to store the details of deleted snapshots.
```
**Functionality**
```
1. Send SNS Notification: Sends an SNS notification with a subject and message.
2. Lambda Handler: Main function that:
Deletes snapshots older than the specified number of days.
Skips snapshots taken by AWS Backup or tagged as 'historical'.
Logs the details of deleted snapshots to an S3 bucket.
Sends SNS notifications for errors and successful deletions.
```

**Deployment**

##### 1. Create Lambda Function:

Go to the AWS Lambda console.
Create a new Lambda function.
Set the runtime to Python 3.x.
Copy and paste the code into the Lambda function editor.
Set Environment Variables:

In the Lambda function configuration, set the environment variables as described above.
Add Permissions:

Ensure the Lambda function has the necessary permissions to access EC2, SNS, and S3.
Test the Function:

Create a test event in the Lambda console and invoke the function to ensure it works as expected.

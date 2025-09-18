# AWS Lambda Function for AMI_Deregister
This AWS Lambda function AMI_Deregister that are older than a specified number of days. It also sends notifications via SNS and logs the details of deleted snapshots to an S3 bucket.

## Prerequisites

- AWS account with necessary permissions
- AWS CLI configured
- Python 3.8 or later
- Boto3 library

  
**Environment Variables**
```
Region_Name: AWS region where the resources are located.
SNS_TOPIC_ARN: ARN of the SNS topic for sending notifications.
DIFF_TIME: Number of days to retain AMI.
BUCKET_NAME: Name of the S3 bucket to store the details of deregistered AMI.
```
**Functionality**
```
1. Send SNS Notification: Sends an SNS notification with a subject and message.
2. Lambda Handler: Main function that:
AMI deregister older than the specified number of days.
Skips AMI taken by AWS Backup or tagged as 'type == historical'.
Logs the details of deregistered AMI to an S3 bucket.
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

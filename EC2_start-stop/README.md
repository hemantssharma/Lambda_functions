# EC2 Instance Start/stop Lambda Function

This AWS Lambda function start/stop specified EC2 instances and sends a notification via SNS.

## Prerequisites

- AWS account with necessary permissions
- AWS CLI configured
- Python 3.8 or later
- Boto3 library


## Deployment

1. **Update the Lambda function code:**

    - Modify the `lambda_handler` function in `lambda_function.py` as needed.
    - Ensure the environment variables are set correctly.

2. **Deploy the Lambda function:**

Click on `Deploy` button to upload the code.


**Functionality**
```
1. Start/stop the specified EC2 instances.
2. Send a notification via SNS with the details of the started/stopped instances.
```

## Error Handling

If an error occurs during execution, the function will return a status code of 500 and the error message.

## Author
```
Hemant Sharma
```

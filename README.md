# AWS Simple File Upload Notification System

## Introduction

This repository contains the Python code and setup instructions for creating an AWS Simple File Upload Notification System. The system monitors an S3 bucket for new file uploads, triggers a Lambda function for processing, sends a notification using Simple Notification Service (SNS), and stores metadata in a Simple Queue Service (SQS) queue for further processing.

## Prerequisites

1. **AWS Account:** Ensure you have an AWS account.
2. **GitHub Repository:** Access the Python code for the Lambda function in the `lambda_function` folder.

## Step-by-Step Implementation

### 1. Create an S3 Bucket

- Open the AWS S3 console and create a new bucket named `notificationsystembucket`.

### 2. Create an SNS Topic and Subscription

- Navigate to the SNS console.
- Create a new topic named `notificationsystemtopic`.
- Subscribe an email to the topic and confirm the subscription.

### 3. Create an SQS Queue

- Go to the SQS console.
- Create a new standard queue named `notificationqueue`.

### 4. Set Up Lambda Function

- Access the Lambda console.
- Create a new function named `notificationsystemfunction` using the Python runtime.
- Create a new execution role with basic Lambda permissions.
- In the execution role, add permissions for SNS and SQS topics.
- Copy and paste the Python Lambda function code from the `lambda_function` folder.
- Set the SNS ARN and SQS URL in the Lambda function.
- Deploy the function.

### 5. Configure S3 Event Trigger

- Go back to the S3 console.
- Add a new event notification to the `notificationsystembucket` with the event name as 'test'.

### 6. Testing

- Upload a file into the S3 bucket.
- Check your email for a notification from `notificationsystemtopic`.
- Debug the Lambda function if needed using CloudWatch logs.
- Access the SQS `notificationqueue` and click on "Send and receive messages" to confirm the message receipt.

## Future Functionality

As you explore and expand the capabilities of your system, consider adding future functionality. For instance, on file upload, you can enhance the system by sending a message to a Lambda function that creates different sizes of images from the original upload and saves them back into the S3 bucket.

## LinkedIn Article

For a detailed walkthrough of this process, check out the accompanying LinkedIn article [here](<LinkedIn_Article_Link>).

Feel free to experiment with additional AWS services and configurations to tailor the system to your specific use case.

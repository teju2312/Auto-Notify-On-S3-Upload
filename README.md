# Auto-Notify-On-S3-Upload

📦 AWS S3 → Lambda → SNS Email Notification System

A fully serverless event-driven project where uploading a file to an Amazon S3 bucket automatically triggers a Lambda function, which then sends an email notification through Amazon SNS.

This project demonstrates a simple, scalable, and real-time notification architecture using AWS services.

🎯 Project Objective

The objective of this project is to create a serverless, event-driven notification system using:

Amazon S3 (file upload trigger)

AWS Lambda (processing logic)

Amazon SNS (email alerts)

Whenever a new object is uploaded to S3, Lambda is triggered and sends an SNS email notification to subscribed users.

📝 Project Description

This project uses AWS managed services to build a lightweight automated alert system:

S3 Bucket stores uploaded files.

S3 Event Trigger notifies Lambda whenever a file is added.

Lambda Function extracts file details and publishes a message to SNS.

SNS Topic sends the message as an email to all subscribed addresses.

This workflow ensures instant alerts every time a file is uploaded, making it useful for:

Log monitoring

Upload validation

Data pipelines

Automated workflows

🔁 Architecture Flow

![Architecture Diagram](https://github.com/teju2312/Auto-Notify-On-S3-Upload/blob/main/lambda%20sns/_-%20visual%20selection.png)

1️⃣ File Upload (S3 Bucket)

![File Upload](https://github.com/teju2312/Auto-Notify-On-S3-Upload/blob/main/lambda%20sns/Screenshot%202025-11-24%20153619.png)
![File Upload](https://github.com/teju2312/Auto-Notify-On-S3-Upload/blob/main/lambda%20sns/Screenshot%202025-11-24%20154159.png)


A user uploads an object into the Amazon S3 bucket.

2️⃣ S3 Event Notification

![Event Notification](https://github.com/teju2312/Auto-Notify-On-S3-Upload/blob/main/lambda%20sns/Screenshot%202025-11-24%20153137.png)

The S3 bucket is configured to trigger Lambda on s3:ObjectCreated:* events.

3️⃣ Lambda Function Execution

![Image URL](https://github.com/teju2312/Auto-Notify-On-S3-Upload/blob/main/lambda%20sns/Screenshot%202025-11-24%20145547.png)
![Image URL](https://github.com/teju2312/Auto-Notify-On-S3-Upload/blob/main/lambda%20sns/Screenshot%202025-11-24%20152621.png)
![Image URL](https://github.com/teju2312/Auto-Notify-On-S3-Upload/blob/main/lambda%20sns/Screenshot%202025-11-24%20152724.png)
![Image URL](https://github.com/teju2312/Auto-Notify-On-S3-Upload/blob/main/lambda%20sns/Screenshot%202025-11-24%20152906.png)


Lambda receives event details such as:
File name
Bucket name
Upload time
Lambda then formats a message and sends it to SNS.

4️⃣ SNS Email Notification

📸 Add Image URL for Step 4:
![SNS EMAIL NOTIFICATION](https://github.com/teju2312/Auto-Notify-On-S3-Upload/blob/main/lambda%20sns/Screenshot%202025-11-24%20154219.png)


SNS sends the email notification to all subscribed users containing:

File name
Bucket
Timestamp
Custom message


---
title: "Blog 3"
date: 2026-07-20
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# AWS Architecture Blog | Building an AWS File Upload Service with Presigned URLs – What I Learned About Serverless Architecture

Hello everyone,

While learning about AWS, I realized that building a file upload system is not simply a matter of creating an API that receives files and stores them in Amazon S3.

At first, I thought that was a reasonable implementation. However, after reading AWS documentation and recommended architectures, I came to understand that routing every file through the Backend forces the system to process a large amount of unnecessary data, especially as the number of users or file sizes increase.

What I learned is that AWS offers a more efficient approach by combining **Presigned URLs** with Serverless services.

![AWS file upload service architecture using a Presigned URL](/images/blog3-presigned-url-architecture.jpg)

## 1. Files do not have to be uploaded through the Backend

The first thing I learned is that the Backend does not need to receive and process all file data directly.

Instead, the Backend is only responsible for authenticating the user and generating a Presigned URL. After receiving this URL, the Client uploads the file directly to Amazon S3.

In my view, this approach significantly reduces the load on the Backend while taking advantage of Amazon S3's scalability.

## 2. How do API Gateway, Lambda, and Amazon S3 work together?

This architecture combines several familiar AWS services:

- **Amazon API Gateway** receives requests from the Client.
- **AWS Lambda** authenticates users and generates Presigned URLs.
- **Amazon S3** stores the uploaded files.
- **AWS IAM** manages access permissions between services.

What I find particularly useful is that Lambda does not process the file data. It only grants temporary permission to upload, which helps the API respond faster and reduces processing costs.

## 3. A successful upload is not the end of the workflow

One point that impressed me is that the system can continue performing many tasks after a file has been uploaded to Amazon S3.

Using S3 Event Notifications or Amazon EventBridge, AWS Lambda can be triggered to:

- Resize images.
- Scan files for viruses.
- Store metadata in a database.
- Send notifications to users.

This separates uploading and file processing into independent steps, making the system easier to extend and scale.

## 4. A good example of Serverless architecture

To me, the most interesting aspect of this architecture is that each service has a clear responsibility. Amazon API Gateway receives requests, AWS Lambda handles business logic, Amazon S3 stores data, and EventBridge supports processing events generated after an upload.

Combining these services keeps the system simple and scalable without requiring server management.

## What I learned

After studying this architecture, I realized that system optimization is not only about choosing more powerful infrastructure. It also depends on making the right design decisions from the beginning.

Presigned URLs prevent the Backend from having to process file data, reduce system load, and fully use the scalability of Amazon S3. At the same time, the event-driven architecture makes it easy to add image processing, virus scanning, or notifications without affecting the user experience.

## Conclusion

For me, this is more than a file upload solution; it is also a representative example of how AWS designs Serverless systems.

Rather than making one component handle every task, AWS encourages us to separate responsibilities across services and combine them into an architecture that is flexible, scalable, and cost-efficient.

If you are learning about Amazon S3 or building a file upload feature on AWS, I think this architecture is well worth exploring.

Thank you for taking the time to read my post. If you have implemented a file upload solution on AWS or have practical experience with Presigned URLs, I would be glad to hear your insights.

**Reference:** [Uploading to Amazon S3 directly from a web or mobile application](https://aws.amazon.com/blogs/compute/uploading-to-amazon-s3-directly-from-a-web-or-mobile-application/)

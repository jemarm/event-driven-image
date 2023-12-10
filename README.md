# AWS Event-Driven Image Processing Pipeline

## Project Overview

This project demonstrates a simple, event-driven image processing pipeline using AWS services. The pipeline is designed to automatically pixelate images uploaded to an S3 bucket and store the processed images in a separate bucket. This demonstrates the integration of AWS Lambda with S3 for serverless computing and automated workflows.

## Architecture

The pipeline uses two Amazon S3 buckets:
1. **Source Bucket**: Where original images are uploaded.
2. **Processed Bucket**: Where pixelated images are stored.

When an image is added to the source bucket, an AWS Lambda function is triggered via a PUT event. The Lambda function is responsible for processing the image.

## Lambda Function

The core of the pipeline is an AWS Lambda function that:
- Is triggered by image uploads (PUT events) in the source S3 bucket.
- Extracts bucket and object information from the event.
- Uses the Python Imaging Library (PIL) to create pixelated versions of the image.

### Pixelation Variations

The Lambda function creates 5 different pixelated variations of each image:
- 8x8 pixels
- 16x16 pixels
- 32x32 pixels
- 48x48 pixels
- 64x64 pixels

These variations are then uploaded to the processed bucket.

## Technologies Used

- **AWS S3**: For storing original and processed images.
- **AWS Lambda**: For executing the image processing logic.
- **Python Imaging Library (PIL)**: For manipulating image pixels.

## Usage

1. Upload an image to the source S3 bucket.
2. The Lambda function will automatically process the image and upload the pixelated versions to the processed bucket.

## Conclusion

This project showcases the power of AWS services in building an automated, serverless image processing pipeline. It demonstrates the practical use of AWS Lambda for event-driven tasks and provides a foundation for more complex image processing and other automated workflows.

---

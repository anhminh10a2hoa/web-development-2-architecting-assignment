# Police Traffic Camera System Design

This document outlines the design of a system to process images captured by police traffic cameras to detect speeding vehicles and potentially issue fines.

## System Overview

The system consists of the following components:

1. **Traffic Cameras**: Capture images of speeding vehicles and their speed.
2. **AWS IoT Core**: Acts as a message broker for IoT devices, receiving data from traffic cameras.
3. **AWS Lambda**: Processes images to extract license plate numbers and query vehicle owner information.
4. **Amazon Rekognition**: Performs image analysis tasks, including optical character recognition (OCR) to extract text from images.
5. **AWS DynamoDB**: Stores extracted license plate numbers and vehicle owner information.
6. **Human Approval Service**: Presents information to a human operator for decision-making.

## Architecture Diagram

[![Alt text](image link)](https://github.com/anhminh10a2hoa/web-development-2-architecting-assignment/blob/master/lecture_exam_3/images/architecture_diagram.png)

## Implementation Details

- **Traffic Cameras**: Actual implementation of traffic cameras capturing images and speed data.
- **AWS IoT Core**: Set up IoT Core to receive messages from traffic cameras.
- **AWS Lambda**: Implement Lambda functions for processing images and querying DynamoDB.
- **Amazon Rekognition**: Configure Rekognition to perform OCR on images.
- **AWS DynamoDB**: Set up DynamoDB tables for storing license plate numbers and vehicle owner information.
- **Human Approval Service**: Implement a service (potentially using API Gateway and Lambda) to present information to human operators for decision-making.

## Data Flow

1. Traffic cameras capture images and speed data.
2. Data is sent to AWS IoT Core.
3. AWS Lambda processes the data, extracts the license plate number, and stores it in DynamoDB.
4. Another Lambda function queries DynamoDB to retrieve vehicle owner information.
5. The Human Approval Service presents the information to a human operator for decision-making.

## Technologies Used

- AWS IoT Core
- AWS Lambda
- Amazon Rekognition
- AWS DynamoDB
- AWS API Gateway (potentially for the Human Approval Service)

## Deployment

Deployment of the system involves setting up the aforementioned AWS services and configuring them according to the described architecture.

## Contributors

Minh Hoang - minh.hoang@tuni.fi

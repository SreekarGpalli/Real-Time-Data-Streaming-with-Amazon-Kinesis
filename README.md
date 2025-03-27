# Real-Time Streaming with Amazon Kinesis

[![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)](https://aws.amazon.com)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)

A personal project demonstrating real-time data streaming using Amazon Kinesis, AWS Lambda, and Kinesis Data Firehose.

![Project Architecture](docs/project_flow.png)

## Overview

This project implements a real-time streaming pipeline that:
1. Generates synthetic geolocation data using a Lambda producer
2. Streams data through Kinesis Data Stream
3. Processes data with a Lambda consumer
4. Archives data in S3 using Kinesis Data Firehose

## Features

- 🌐 Real-time data generation with synthetic GPS coordinates
- 🔄 Kinesis Data Stream for durable data ingestion
- 🚀 Serverless architecture using AWS Lambda
- 📦 Data persistence with Kinesis Firehose & S3
- 📊 CloudWatch integration for monitoring

## Prerequisites

- AWS Account
- AWS CLI configured with proper credentials
- IAM permissions to create:
  - Kinesis Streams
  - Lambda Functions
  - IAM Roles
  - S3 Buckets
- Python 3.11+

## Architecture

```mermaid
graph TD
    A[Producer Lambda] -->|Put records| B[Kinesis Data Stream]
    B -->|Trigger| C[Consumer Lambda]
    B -->|Firehose| D[S3 Bucket]
    C -->|Logs| E[CloudWatch]
    D -->|Data Files| F[Analytics]

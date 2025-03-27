### 1. Create an IAM role using given file name it **`KinesisLambdaRole`**
### 2. Create a Kinesis Data Stream

- **Service**: Amazon Kinesis
- **Stream Name**: `TelemetricsStream`
- **Capacity Mode**: On-demand

### 2. Develop the Producer Lambda Function

This Lambda function continuously sends telemetry events to the Kinesis Data Stream.

#### Steps:
1. Create a Lambda function named **`produceKinesisEvents`** using Python.
2. Use an existing KinesisLambdaRole IAM role 
3. Insert the following code in `producer_lambda/produceKinesisEvents.py`:

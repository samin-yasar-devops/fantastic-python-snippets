
```markdown
# EC2 Management Lambda Function

This Python code defines a Lambda function for managing Amazon Elastic Compute Cloud (EC2) instances. The function provides the following actions:

1. List EC2 Instances: Retrieves information about all EC2 instances in the specified region.
2. Start an EC2 Instance: Initiates the start of a specific EC2 instance.
3. Stop an EC2 Instance: Initiates the stop of a specific EC2 instance.

## Configuration

Before using this Lambda function, ensure that you have set the appropriate AWS credentials and region in your environment. You can also configure the region within the code.
```
```python
region = 'ap-southeast-1'  # Change this to your desired AWS region
ec2 = boto3.resource('ec2', region_name=region)
ec2_client = boto3.client('ec2', region_name=region)
```

## Usage

### List EC2 Instances

To list all EC2 instances in the region, make an HTTP GET request to the Lambda function with the `action` parameter set to "list."

Example:

```http
GET /your-lambda-endpoint?action=list
```

### Start an EC2 Instance

To start a specific EC2 instance, make an HTTP GET request to the Lambda function with the `action` parameter set to "start" and provide the `id` parameter with the instance ID.

Example:

```http
GET /your-lambda-endpoint?action=start&id=your-instance-id
```

### Stop an EC2 Instance

To stop a specific EC2 instance, make an HTTP GET request to the Lambda function with the `action` parameter set to "stop" and provide the `id` parameter with the instance ID.

Example:

```http
GET /your-lambda-endpoint?action=stop&id=your-instance-id
```

### Error Handling

If any request contains invalid or missing parameters, the Lambda function will return a 400 Bad Request response with an error message.

## License

This code is provided under the MIT License.

## Author
```
[M Samin Yasar]

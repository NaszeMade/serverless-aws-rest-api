# Step 3: Lambda Function Setup

## Overview:
The AWS Lambda Function is crucial because it ensures that the Lambda function has permission to access the DynamoDB table and perform the necessary CRUD operations. Lambda functions handle the core logic of the application, triggered by API Gateway.

## Steps:
1. **Navigate to the AWS Console**:
   - Find the `Lambda` service > `Dashboard` > `Create function`.
2. **Fill In the function editor**:
   - Choose the `Author from scratch` option, fill in the name and choose runtime (Python).
   - Under `Execution role`, choose `Use an existing role` and choose the role made in step 2.
   - Click `Create function`
3. **Code Source**:
   - Replace the default code source with the following
     `import boto3
import json

print('Loading function')

def lambda_handler(event,context):
    '''Provide an event that contains the following keys:

      - operation: one of the operations in the operations dict below
      - tableName: required for operations that interact with DynamoDB
      - payload: a parameter to pass to the operation being performed '''
    
    print('Received event: ' + json.dumps(event, indent = 1))
     
    operation = event['operation']
    

    if 'tableName' in event:
        dynamo = boto3.resource('dynamodb').Table(event['tableName'])

    operations = {
    #CRUD operations shown below:
        'create': lambda x: dynamo.put_item(**x),
        'read': lambda x: dynamo.get_item(**x),
        'update': lambda x: dynamo.update_item(**x),
        'delete': lambda x: dynamo.delete_item(**x),
        'echo': lambda x: x
    }

    if operation in operations:
        return operations[operation](event.get('payload'))
    else:
        raise ValueError('Unrecognized operation "{}"'.format(operation)) `
   - Click `Deploy`.

This Lambda function will now be ready to handle CRUD operations with DynamoDB as specified by the event payload, performing actions such as creating, reading, updating, or deleting items in the specified DynamoDB table.

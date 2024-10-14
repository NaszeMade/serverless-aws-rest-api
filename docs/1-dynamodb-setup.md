# Step 1: AWS DynamoDB Setup

## Overview:
AWS DynamoDB is a fully managed NoSQL database that provides fast and predictable performance. It is used in this setup to store and manage the data for the REST API. DynamoDB's scalability and serverless nature make it an ideal choice for handling backend data in a serverless architecture.

## Steps:
1. **Navigate to the AWS Console**:
   - Find the `DynamoDB` service > `Create table`.
2. **Fill In the Table Details**:
   - Fill in the table name and partition key.
3. **Create Table**:
   - Leave everything else as default and create the table.

## Screenshot:

## Conclusion:
Once the DynamoDB table is created, it will serve as the data store for your serverless REST API. The table will store items or records that can be accessed, updated, and deleted via the API. This marks the first step in configuring the backend of your serverless API using AWS DynamoDB.

# Step 2: AWS Lambda IAM Role Setup

## Overview:
The AWS Lambda IAM role is very crucial because it makes sure that the lambda function has permission to access the DynamoDB table.

## Steps:
1. **Navigate to the AWS Console**:
   - Find the `IAM` service > `Policies` > `create policy`.
2. **Fill In the JSON policy editor**:
   - Give me the limit of function, the ability to basically edit the items in the DynamoDB.
   - Watch the CloudWatch Stream (optional).
3. **Review and Create**:
   - After all the information is filled out click next.
   - enter the policy name and add a optional description.
4. **Navigate back to the IAM Dashboard**:
   - Find the `Roles` > `Create roles`.
5. **Creating the role**:
   - Select `AWS service` trusted entity type and select `Lambda` as the use case
   - Selected the newly created policy for the `Add Permissions` step.
   - Enter the Role name and an optional description

## Screenshot:

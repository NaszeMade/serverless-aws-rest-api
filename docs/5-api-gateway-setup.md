# Step 5: API Gateway Setup

## Overview:
The AWS API Gateway is critical for exposing your Lambda functions as RESTful endpoints that clients can access over HTTP. It serves as the entry point to the serverless API, handling all routing, security, and request management. API Gateway enables you to define routes, manage traffic, set up throttling and authorization, and seamlessly integrate with other AWS services like Lambda. By connecting API Gateway to your Lambda functions, you can build a scalable, secure, and fully managed REST API without the need to manage infrastructure.

## Steps:
### 1. **Open API Gateway in AWS Management Console**
   - Navigate to the [API Gateway Console](https://console.aws.amazon.com/apigateway).
   - Click **Create API** to begin setting up your API.
### 2. **Create a New REST API**
   - Select **REST API** under the API type.
   - Choose **New API** and provide:
     - **API Name**: Give your API a meaningful name (e.g., `ServerlessRestAPI`).
     - **Description**: Optionally add a description for future reference.
     - **Endpoint Type**: Choose **Regional** for a standard setup, or **Edge-Optimized** if your API will be used globally.
### 3. **Create Resources and Methods**
   - **Create a Resource**: This represents an endpoint (e.g., `/items`).
     - Click **Actions**, then **Create Resource**.
     - Define the **Resource Name** (e.g., `items`) and leave **Enable API Gateway CORS** checked.
   - **Add Methods**: Define the HTTP methods (GET, POST, PUT, DELETE) for each resource.
     - Click **Actions**, then **Create Method**.
     - Select the HTTP method (e.g., `GET`) and set the **Integration Type** to **Lambda Function**.
     - Choose the region of your Lambda function and type its name.


   - Create a new **Deployment Stage** (e.g., `dev`, `prod`).
   - After deploying, you’ll be provided with an **Invoke URL** for the deployed API (e.g., `https://<api-id>.execute-api.<region>.amazonaws.com/prod`).

### 7. **Test the API**
   - Copy the **Invoke URL** and append the resource path (e.g., `/items`) to test the API.
   - Use an HTTP client like Postman or curl to send requests to your API (e.g., GET, POST, PUT, DELETE).

By following these steps, your API Gateway will be set up to route requests to the Lambda functions, forming the backbone of your serverless REST API.

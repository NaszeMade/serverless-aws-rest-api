# Step 6: API Deployment Setup

## Overview:
This step is setting up the serverless REST API and deploying it to a specific stage. Deployment makes the API publicly accessible, allowing it to be invoked by clients using the provided URL.

## Steps:

1. **Deploying the API**:
   - After the API is sucessfully created, find and click the `Deploy API` button.
   - In the `Stage` option, choose `*New stage*` and provide the stage name.
   - Click `Deploy` to publish the API to the stage.

2. **Get the `POST` URL**:
   - After deployment is successful, expand the stage name to reveal the `POST` method.
   - Locate the `POST` method and copy the `Invoke URL`.
   - The Invoke URL is used by clients to interact with the API.

## Screenshots:

## Conclusion:
With the API now deployed, your serverless REST API is live and ready for use. The API Gateway allows for the management of different stages (like development, testing, and production), giving the flexibility in testing and deploying updates. Clients can use the **Invoke URL** to interact with your backend, powered by Lambda and DynamoDB. This concludes the setup for a fully functional, scalable, and serverless REST API using AWS.

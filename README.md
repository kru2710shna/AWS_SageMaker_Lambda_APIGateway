# Deploying a Machine Learning Model on AWS for Breast Cancer Diagnosis Prediction

This project demonstrates how to deploy a pre-trained Machine Learning (ML) model on **Amazon Web Services (AWS)** to provide AI-based predictions through a cloud-hosted API. The architecture leverages **Amazon SageMaker**, **AWS Lambda**, and **Amazon API Gateway** to create a seamless workflow where users can submit data from the public internet and receive near-instant predictions from the ML model.

---

## Workflow Overview

1. **User Interaction**: A public user submits input data through the API.
2. **API Gateway**: Receives the request using a REST API interface and forwards it to a Lambda function.
3. **Lambda Function**: Acts as a bridge to the SageMaker endpoint, sending user data to the model for predictions.
4. **SageMaker Endpoint**: Hosts the pre-trained ML model, processes input data, generates a prediction, and sends the result back via Lambda to the API Gateway.
5. **Response Delivery**: The predicted value is returned to the user.

---

## Technical Components

### **1. Amazon SageMaker**
- Used to train and deploy the ML model.
- Stores the trained model artifacts in an S3 bucket.
- Creates an endpoint for real-time predictions.

### **2. AWS Lambda**
- Handles the business logic and integrates the ML endpoint with the API Gateway.
- Processes input data and forwards predictions to the user.

### **3. Amazon API Gateway**
- Exposes the Lambda function as a REST API for public access.

### **4. IAM Roles and Policies**
- Ensures secure access between SageMaker, Lambda, and API Gateway.
- Configures permissions for all components.

---

## Use Case

The deployed architecture solves the **breast cancer diagnosis prediction** problem.  
The ML model, trained using a **SageMaker notebook template**, predicts whether breast cancer is malignant or benign based on input features.

---

## Steps to Build the Architecture

1. **Set up a SageMaker Notebook Instance** and train the model using a Jupyter notebook.
2. **Deploy the model** and create a SageMaker Endpoint.
3. **Configure an AWS Lambda Function** to interact with the endpoint.
4. **Set up an Amazon API Gateway** to expose the Lambda function as a REST API.
5. **Test the architecture** by sending data through the API and verifying predictions.

---

## Key Tools and Services

- **AWS Console**: For hands-on setup of services.
- **Python**: Used for scripting in SageMaker and Lambda.
- **Jupyter Notebook**: For model training and evaluation in SageMaker.

---

## Project Highlights

This project demonstrates a scalable and efficient approach to deploying ML models on the cloud, enabling real-time predictions for end users.  


## Answering Some Questions

### User Interaction

What happens?
End-users interact with the system by providing input data through a web interface or application.
Purpose:
The users aim to leverage AI insights by submitting specific input data (e.g., text, images, or other formats) for analysis.

### Input Data Sent to API Gateway

What happens?
The input data is forwarded to Amazon API Gateway, which serves as the entry point for the system.
Purpose:
API Gateway acts as a REST API endpoint to securely accept, process, and route user input data to the appropriate backend service.

### API Gateway Sends Data to AWS Lambda

What happens?
After receiving the input, Amazon API Gateway triggers an AWS Lambda function, passing along the user data.
Purpose:
Lambda functions handle the business logic, processing, and routing of the request to the next step in the workflow.

### AWS Lambda Invokes SageMaker Endpoint

What happens?
AWS Lambda sends the input data to the Amazon SageMaker Endpoint, which hosts the pre-trained machine learning model.
Purpose:
The Lambda function triggers the SageMaker Endpoint with the task of making a prediction using the input data.
The model processes the input and generates an output (e.g., prediction or insight).

## ML Model Processing in SageMaker

What happens?
The SageMaker instance loads the machine learning model (stored as a binary file) to handle the prediction request.
The trained model processes the input data and generates a response.
Purpose:
To perform the core AI/ML task (e.g., classification, regression, or text generation) and return actionable insights.

## Model Endpoint Sends Prediction to Lambda

What happens?
The SageMaker Endpoint returns the predicted results or insights to the AWS Lambda function.
Purpose:
To relay the processed response from the model back to the Lambda function for further processing or routing.

## Lambda Sends Response to API Gateway

What happens?
The Lambda function sends the prediction result (in the required format) back to the Amazon API Gateway.
Purpose:
To ensure that the response is appropriately formatted and routed back to the user.

## User Receives Prediction

What happens?
The API Gateway sends the processed prediction or insights back to the end-user interface.
Purpose:
To complete the cycle, delivering the model’s insights to the user in a seamless and efficient manner.



This workflow provides a scalable, serverless architecture for deploying and utilizing machine learning models with Amazon SageMaker. It ensures efficient data handling, processing, and response delivery using AWS Lambda and API Gateway as intermediary layers


## Refrence 
https://aws.amazon.com/blogs/machine-learning/call-an-amazon-sagemaker-model-endpoint-using-amazon-api-gateway-and-aws-lambda/

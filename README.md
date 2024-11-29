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


## Refrence 
https://aws.amazon.com/blogs/machine-learning/call-an-amazon-sagemaker-model-endpoint-using-amazon-api-gateway-and-aws-lambda/

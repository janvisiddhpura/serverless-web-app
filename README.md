# Serverless Web Application with AWS Lambda, API Gateway, and DynamoDB 🎬

#### This project demonstrates the deployment of a serverless web application using AWS Lambda for backend logic, Amazon API Gateway for REST endpoints, and Amazon DynamoDB for data storage. Designed for scalability and cost-efficiency! 🛠️

### 📝 Architecture Overview

- **AWS Lambda:** ⚡ Handles backend logic for HTTP requests.

- **Amazon API Gateway:** 🌐 Manages REST API endpoints and routes requests.

- **Amazon DynamoDB:** 💾 Stores and retrieves application data.

- **AWS IAM:** 🔐 Manages permissions and access control.

### 🛠️ Prerequisites

- **AWS Account:** 🏦 AWS account with admin/IAM privileges.

- **AWS CLI:** (Optional) 💻 For advanced deployments.

- **Basic knowledge of AWS Console 🖥️**

### 🧰 Setup Instructions

#### 1️⃣ IAM Role Configuration

- **Role Name:** admin-lambda-role

- **Attached Policies:**

  - AmazonDynamoDBFullAccess

  - AWSLambdaBasicExecutionRole

- **Steps:**

1. Go to IAM Console 🚪

2. Create role:

    AWS Service → Lambda

3. Attach policies:

    AmazonDynamoDBFullAccess

    AWSLambdaBasicExecutionRole

4. Name: admin-lambda-role

5. Finish creation ✅

#### 2️⃣ Lambda Function

- **Function Name:** berryStaticFunction

- **Region:** ap-south-1 (Deploy here only; do not use us-east-1)

- **Execution Role:** Use existing role admin-lambda-role

- **Runtime:** Choose your preferred runtime (Node.js, Python, etc.)

- **Steps:**

1. Open Lambda Console 🚀

2. Create a function

3. Name: berryStaticFunction

4. Select runtime & region: ap-south-1

5. Permissions: Use existing role admin-lambda-role

6. Deploy & test code 🧪

#### 3️⃣ DynamoDB

- **Table Name:** berry-contacts

- **Primary Key:** Configure as per your needs

- **Steps:**

1. Open DynamoDB Console 📊

2. Create a table

3. Name: berry-contacts

4. Define primary key (e.g., email as partition key)

5. Finish creation ✅

#### 4️⃣ API Gateway

- **API Name::** berrycontactsapi

- **Methods:**

  - GET 📥 (Fetch data)
 
  - POST 📤 (Create/update data)

- **Stage:** dev

- **Steps:**

1. Open API Gateway Console 🌐

2. Create API → REST API

3. Name: berrycontactsapi

4. Add resource & methods:

  -  GET

  -  POST

5. Integrate with Lambda function: berryStaticFunction

6. Deploy to dev stage 🚀

### 🧪 Testing

- **GET Method:** Use Postman or cURL to fetch data.

- **POST Method:** Send a POST request to create/update data.

### Example cURL for POST:

```sh
curl -X POST https://{your-api-id}.execute-api.ap-south-1.amazonaws.com/dev/resource \
  -H "Content-Type: application/json" \
  -d '{"key": "value"}'
```

### Security & Best Practices

- **Least Privilege:** Use minimal IAM permissions for production 🔏

- **API Keys:** Enable API keys for usage plans and throttling 🔑

- **CORS:** Configure CORS if the frontend is hosted separately 🌍 

### 💡 Support

- For troubleshooting or enhancements, consult AWS docs and community forums. Infrastructure as Code (IaC) tools like AWS CloudFormation or Terraform are recommended for repeatable deployments

<div id="user-content-toc">
<ul style="list-style: none;">
<summary>
  <h2> Happy scripting!🚀 </h2>
</summary>
</ul>
</div>

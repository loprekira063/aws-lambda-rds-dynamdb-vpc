# 🚀 Serverless Feedback System on AWS

A serverless web application built on AWS where users can submit feedback and admins can store and view structured data securely.

This project demonstrates real-world AWS concepts like IAM, Lambda networking, CORS handling, and the difference between NoSQL and SQL databases.

---

## 🧠 Project Overview

- Static website hosted on **Amazon S3**
- Public user feedback stored in **DynamoDB**
- Admin feedback stored in **Amazon RDS (MySQL)**
- **Two separate AWS Lambda functions** for clean architecture
- **API Gateway** for backend communication
- Secure access using **IAM roles**
- Fully serverless (no EC2)

---

## 🏗️ Architecture

# 🚀 Serverless Feedback System on AWS

A serverless web application built on AWS where users can submit feedback and admins can store and view structured data securely.

This project demonstrates real-world AWS concepts like IAM, Lambda networking, CORS handling, and the difference between NoSQL and SQL databases.

---

## 🧠 Project Overview

- Static website hosted on **Amazon S3**
- Public user feedback stored in **DynamoDB**
- Admin feedback stored in **Amazon RDS (MySQL)**
- **Two separate AWS Lambda functions** for clean architecture
- **API Gateway** for backend communication
- Secure access using **IAM roles**
- Fully serverless (no EC2)

---

## 🏗️ Architecture

S3 Static Website
|
v
API Gateway
|
v
User Lambda Admin Lambda
| 
v
DynamoDB RDS (MySQL) || RDS

---

## 🧩 AWS Services Used

- Amazon S3 (Static Website Hosting)
- Amazon API Gateway
- AWS Lambda
- Amazon DynamoDB
- Amazon RDS (MySQL)
- AWS IAM
- AWS VPC (for RDS access)

---

## 🔍 Key Design Decisions

- **Separated Lambda functions** for DynamoDB and RDS to avoid VPC networking issues
- Used **Lambda Proxy Integration**
- Implemented **CORS handling inside Lambda** responses
- Followed **least privilege IAM policies**
- Avoided hardcoded credentials using IAM roles

---

## ⚠️ Challenges Faced & Solutions

### 1. Lambda Timeout in VPC
- **Problem:** DynamoDB calls timed out when Lambda was inside a VPC
- **Solution:** Split Lambdas based on network requirements

### 2. IAM Access Denied Errors
- **Problem:** Lambda could not write to DynamoDB
- **Solution:** Attached least-privilege IAM policies

### 3. CORS Errors in Browser
- **Problem:** Browser blocked API calls
- **Solution:** Returned CORS headers directly from Lambda due to proxy integration

### 4. Verifying RDS Data
- **Problem:** Could not confirm if RDS inserts were happening
- **Solution:** Added admin fetch functionality in Lambda

---

## 🧪 Features

- User feedback submission
- Admin feedback submission
- Admin-only RDS data view
- Role-based frontend behavior
- Secure backend communication

---

## ▶️ How It Works

1. User opens the S3-hosted website
2. Feedback is sent via `fetch()` to API Gateway
3. API Gateway triggers Lambda
4. Data is stored in DynamoDB or RDS depending on role
5. Admin can fetch and view RDS data

---

## 📌 What I Learned

- Difference between DynamoDB and RDS networking
- Importance of IAM permissions
- How CORS works with API Gateway & Lambda
- Real-world debugging of serverless applications
- Why clean architecture matters in cloud systems

---

## 🔮 Future Improvements

- Add authentication for admin access
- Use AWS Cognito
- Add pagination for RDS data
- CloudWatch monitoring & alerts
- Infrastructure as Code (Terraform / CloudFormation)

---

## 🙌 Acknowledgements

This project was built as a hands-on learning experience to understand AWS serverless architecture and real-world cloud challenges.

# The Ultimate AWS Serverless Deployment: Lambda + API Gateway [Step-by-Step Project]

---

## 1. Create a DynamoDB Table

- Go to DynamoDB in AWS Console.
- Click **Create table**.
  - **Table name:** `Karthik`
  - **Partition key:** `email`
- Click **Create table**.

---

## 2. Create an IAM Role for Lambda

- Go to **IAM > Roles**.
- Click **Create role**.
  - **Trusted entity type:** AWS Service
  - **Use case:** Lambda
- Attach the **AdministratorAccess** policy.
- **Role name:** `Lambda-Role`
- Click **Create role**.

---

## 3. Create a Lambda Function

- Go to **Lambda > Create function**.
  - **Function name:** `Karthik`
  - **Runtime:** Python 3.13
  - **Permissions:** Use an existing role (`Lambda-Role`)
- After creation, go to **Configuration > General configuration > Edit**.
  - **Timeout:** 15 minutes 0 seconds
- Upload your code in the **Code** section.

---

## 4. Create an API Gateway

- Go to **API Gateway > Create API**.
  - Choose **REST API** (Build).
  - **API name:** `Lambda`
- Create a **GET** method:
  - **Integration type:** Lambda proxy integration (Enable)
  - **Lambda function:** Select your Lambda function
- Create a **POST** method:
  - **Integration type:** Lambda proxy integration (Enable)
  - **Lambda function:** Select your Lambda function
- Deploy the API:
  - **Stage name:** `dev`
- Copy the **Invoke URL** (e.g., `https://xxxxxx.execute-api.ap-south-1.amazonaws.com/dev`).

---

<!-- ## 5. Create an ACM Certificate

- Go to **AWS Certificate Manager (ACM)**.
- Request a public certificate for your custom domain (e.g., `api.konakarthikeya.xyz`).
- Complete domain validation as instructed.

---

## 6. Access API Gateway via Custom Domain

- In **API Gateway**, go to **Custom domain names**.
- Click **Create** or **Add domain name**.
  - **Domain name:** `api.konakarthikeya.xyz`
  - Attach the ACM certificate.
- Configure **API mappings**:
  - **API:** `Lambda`
  - **Stage:** `dev`
  - **Path (optional):** `dev`

---

## 7. Add a Record in Route 53

- Go to **Route 53 > Hosted zones**.
- Create a new **Record**:
  - **Record name:** `api`
  - **Record type:** Alias
  - **Alias to:** API Gateway domain
  - **Region:** Select your region
  - **Value:** Select the API Gateway URL

--- -->



## Clean-up

- Api Gateway
- lambada
- Dynamo DB

**Done! Your serverless Lambda API is now accessible via your custom domain.**

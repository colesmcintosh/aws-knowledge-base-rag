# Querying a Knowledge Base with AWS Bedrock

This notebook demonstrates how to query an AWS Bedrock Knowledge Base using the `RetrieveAndGenerate` API. It walks you through setting up the AWS Bedrock Runtime client, retrieving available foundation models, and executing a query to generate structured responses. This demo showcases the power of AWS Bedrock for both advanced AI functionality and data privacy.

## Prerequisites
Before running the notebook, ensure that you have met the following requirements:
- **Boto3 Installed**: Install the AWS SDK for Python with:
  ```sh
  pip install boto3
  ```
- **AWS Credentials Configured**: Set up your AWS credentials using environment variables or the AWS CLI.
- **Knowledge Base Setup**: Have an AWS Bedrock Knowledge Base configured, and be ready with your AWS identifiers:
  - `AWS_ACCESS_KEY`
  - `AWS_SECRET_KEY`
  - `AWS_KNOWLEDGE_BASE_ID`
  - `AWS_MODEL_ARN`

## Overview
The notebook is structured into several key parts:

1. **Initialization and Client Setup**  
   The notebook begins by importing necessary libraries and initializing AWS Bedrock clients for runtime operations and foundation model retrieval. This ensures proper authentication and connectivity to AWS services.

2. **Retrieving Foundation Models**  
   A section queries AWS Bedrock to fetch available foundation models. This helps you determine which models are accessible for generating responses and select the appropriate model for your query.

3. **Configuring Query Parameters**  
   You define the question text, specify your knowledge base ID, and provide the model ARN. This configuration builds the payload that is sent to AWS Bedrock for processing your query.

4. **Query Execution and Response Retrieval**  
   The notebook sends the query using the `RetrieveAndGenerate` API. The response includes generated text, citations with source references, and a session ID for maintaining conversational context.

5. **Parsing and Displaying Results**  
   Finally, the notebook includes logic to parse and display the response in a clear, human-readable format, making it easy to review the generated answer and access relevant source documents.

## Security and Compliance with AWS Bedrock
Amazon Bedrock provides a robust security and data privacy framework that is ideal for generative AI applications. Key security features include:

- **Full Data Control**:  
  You have complete control over the data used to customize foundation models. Data is encrypted both in transit and at rest. Moreover, you can create, manage, and control encryption keys using AWS Key Management Service (AWS KMS), while identity-based policies allow you to specify which actions can be performed by users and roles.

- **Comprehensive Data Protection and Privacy**:  
  When tuning a foundation model, Amazon Bedrock works with a private copy of the model, ensuring that your data is not shared with model providers or used to improve the base models. Additionally, you can use AWS PrivateLink to establish private connectivity from your Amazon VPC to Amazon Bedrock, keeping your data isolated from internet exposure. Bedrock meets various compliance standards such as ISO, SOC, CSA STAR Level 2, HIPAA eligibility, GDPR compliance, and is FedRAMP High authorized in AWS GovCloud (US-West).

- **Governance and Auditability**:  
  AWS Bedrock offers comprehensive monitoring and logging through Amazon CloudWatch and AWS CloudTrail. These services help you track usage, monitor API activity, and build dashboards for audit purposes. You can also store metadata, requests, and responses in Amazon S3 or CloudWatch Logs. Automated abuse detection mechanisms further enhance security by preventing misuse.

For more detailed information, please visit the [AWS Bedrock Security and Compliance page](https://aws.amazon.com/bedrock/security-compliance/).

---

This demo notebook serves as a technical illustration of how to leverage AWS Bedrock for secure, privacy-focused generative AI applications.

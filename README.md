# **Event Driven Serverless Data-Analytics Architecture Project on AWS**


## Hands-on Project: **Real-Time Clickstream Data Analytics for Restaurant Insights**

## Project Synopsis:

This project is designed to provide real-time analytics for a restaurant's menu items based on clickstream data. The goal is to derive actionable insights for a restaurant owner by architecting a data analytics solution using managed services on AWS. The architecture leverages serverless and event-driven components, ensuring scalability, cost efficiency, and real-time processing of data.

## Architecture Diagram

![Cloud Architecture](https://github.com/KireetiChennuru/Event-Driven-Serverless-Data-Analytics-Architecture/blob/main/Project_Files/Cloud%20Architecture.jpeg)

## Services Used

- **AWS Identity and Access Management (IAM):**
- **Amazon Simple Storage Service (Amazon S3):**
- **AWS Lambda:**  
- **Amazon Kinesis Data Firehose:**  
- **Amazon API Gateway:**  
- **Amazon Athena:**  
- **Amazon QuickSight:**    

## Architecture Diagram Core Aspects:

### Create IAM Policies and Roles:
- Created an IAM role that enables API Gateway to send streaming data to Amazon Kinesis Data Firehose and added the API-Firehose policy to the role.
- IAM roles are used to delegate access to users, applications, or services that don't normally have access to the AWS resources.
  
  ![IAM Policies and Roles](https://github.com/KireetiChennuru/Event-Driven-Serverless-Data-Analytics-Architecture/blob/main/Project_Files/Creating%20custom%20IAM%20policies.jpg)
  - [View AWS Identity and Access Management on AWS](https://aws.amazon.com/iam/)

### Create an S3 Bucket:
- Created an object storage bucket in Amazon S3 to store incoming clickstream data.
- Amazon S3 offers industry-leading scalability, data availability, security, and performance. It is used to store and protect any amount of data for a range of use cases, such as data lakes, websites, mobile applications, backup and restore etc,
  
  ![S3 Bucket](https://github.com/KireetiChennuru/Event-Driven-Serverless-Data-Analytics-Architecture/blob/main/Project_Files/Creating%20an%20S3%20bucket.jpg)
  - [Learn more about Amazon S3](https://aws.amazon.com/s3/)

### Create a Lambda Function:
- Created a Lambda function that transforms incoming data before Amazon Kinesis Data Firehose and ingests it into the object storage bucket.
- With AWS Lambda serverless architecture, there is no need to provision or maintain servers, handle OS updates, or manage scaling manually. You can organize your code into Lambda functions and it runs your function only when needed and scales automatically. You only pay for the compute time that you consume.
  
  ![Lambda Function](https://github.com/KireetiChennuru/Event-Driven-Serverless-Data-Analytics-Architecture/blob/main/Project_Files/Creating%20a%20Lambda%20function.jpg)
  - [Learn more about AWS Lambda](https://aws.amazon.com/lambda/)

### Create a Kinesis Data Firehose Delivery Stream:
- Created a Kinesis Data Firehose delivery stream to ingest streaming data and  deliver it to the Amazon S3 bucket. 
- Amazon Kinesis is used to collect, process, and analyze real-time, streaming data so you can get timely insights and analyze the data and respond instantly as it arrives, Instead of waiting until the entire data is collected before the processing can begin.
  
  ![Kinesis Data Firehose Delivery Stream](https://github.com/KireetiChennuru/Event-Driven-Serverless-Data-Analytics-Architecture/blob/main/Project_Files/Creating%20a%20Kinesis%20Data%20Firehose%20delivery%20stream.jpg)
  ![Adding the Firehose delivery stream ARN to the S3 bucket](https://github.com/KireetiChennuru/Event-Driven-Serverless-Data-Analytics-Architecture/blob/main/Project_Files/Adding%20the%20Firehose%20delivery%20stream%20ARN%20to%20the%20S3%20bucket.jpg)
  - [Learn more about Amazon Kinesis Data Firehose](https://aws.amazon.com/kinesis/data-firehose/)

### Create a REST API:
- Created a REST API in API Gateway. This API serves as a communication gateway between our application and AWS services.
- A REST API in API Gateway is a collection of resources and methods that are integrated with backend HTTP endpoints, Lambda functions, or other AWS service. It will act as an interface between two computer systems to exchange information securely over the internet.
- An API, or Application Programming Interface, is a set of rules and protocols that allows different software applications to communicate with each other.
  
  ![REST API](https://github.com/KireetiChennuru/Event-Driven-Serverless-Data-Analytics-Architecture/blob/main/Project_Files/Creating%20an%20API%20in%20API%20Gateway.jpg)
  ![Integration Successful](https://github.com/KireetiChennuru/Event-Driven-Serverless-Data-Analytics-Architecture/blob/main/Project_Files/Integration%20Request%20-%20Mapping%20Templates.jpg)
  - [Learn more about Amazon API Gateway](https://aws.amazon.com/api-gateway/)

### Create an Amazon Athena Table:
- Created a table in Athena using AWS Management console and we can run a Structured Query Language (SQL) query to view the payloads which was ingested with the REST API.
- Amazon Athena is an interactive query service that makes it easy to analyze data directly in Amazon S3 using standard SQL.Athena provides a simplified, flexible way to analyze petabytes of data where it lives or build applications from an Amazon S3 data lake or other cloud systems using SQL or Python.
  
  ![Amazon Athena](https://github.com/KireetiChennuru/Event-Driven-Serverless-Data-Analytics-Architecture/blob/main/Project_Files/Creating%20an%20Athena%20table.jpg)
  ![Athena Query Successful](https://github.com/KireetiChennuru/Event-Driven-Serverless-Data-Analytics-Architecture/blob/main/Project_Files/Athena%20Query%20Successful.jpg)
  - [Learn more about Amazon Athena](https://aws.amazon.com/athena/)

### Create Amazon QuickSight Dashboards:
- Once the clickstream data is processed successfully, we can use QuickSight to build dashboards in Amazon QuickSight to visualize the analyzed data.
- Amazon QuickSight is a cloud-scale business intelligence (BI) service that you can use to deliver easy-to-understand insights. It allows users to build visualizations, perform ad-hoc analysis, and get business insights from their data. QuickSight connects to data in the cloud and combines data from various sources.
  
 ![Amazon QuickSight](https://github.com/KireetiChennuru/Event-Driven-Serverless-Data-Analytics-Architecture/blob/main/Project_Files/Quicksight%20Dashboard.jpg)
  - [Learn more about Amazon QuickSight](https://aws.amazon.com/quicksight/)


## Project Goals

The primary goal of this project is to design an architecture that ingests, stores, and visualizes clickstream data in real time. The customer, a restaurant owner, aims to gain insights into the performance of menu items ordered in their establishment. Due to limited staff and resources, the architecture utilizes AWS managed services, ensuring minimal maintenance and operational overhead.

## Project Structure

#### Task 1: Create IAM policies and roles to follow the best practices of working in the AWS Cloud.

#### Task 2: Creating an object storage S3 bucket to store clickstream data.

#### Task 3: Create the Lambda function for Amazon Kinesis Data Firehose to transform data.

#### Task 4: Create a Kinesis Data Firehose delivery stream to deliver real-time streaming data to Amazon S3.

#### Task 5: Adding the Firehose Delivery Stream ARN to the S3 Bucket

#### Task 6: Create a REST API to insert data.

#### Task 7: Create an Amazon Athena table to view the obtained data.

#### Task 8: Create Amazon QuickSight dashboards to visualize data.

#### Task 9: Deleting All Resources

<br>


## Author

- Kireeti Chennuru | www.linkedin.com/in/kireeti-chennuru

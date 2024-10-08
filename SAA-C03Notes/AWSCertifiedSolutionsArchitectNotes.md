# AWS Certified Solutions Architect Study Guide Notes - Associate (SAA-C03) Forth Edition

## Introduction

These notes were taken from the _AWS Certified Solutions Architect Study Guide_ Book written by Ben Piper and David Clinton.  Feel free to use these notes, but check them for accuracy.

## Chapter 1 Introduction to Cloud Computing and AWS
### Cloud Computing and Virtualization

The core of the cloud is virtualization. Virtualization makes it possible to deploy a virtual service from resources of a physical server. 

**Note:** See [Server Virtualization: The Basics](https://github.com/hamiltonrichard/CLF-CO2Notes/blob/main/AWSCertifiedCloudPractitionerStudyNotes.md#server-virtualization-the-basics) in my Cloud Paractitioner notes. 

__Cloud Computing Architecture__

Cloud providers have enormous server farms that are used to create the cloud environment. 

Cloud platforms provide a computing platform that offers on-demand,self-service access to pooled resources. Your usage is metered and billed according to your usage.

__Cloud Computing Optimization__

Cloud computing is a great choice for running workloads. Cloud computing scalable, elastic and cost effective. 

_Scalability_

Scalabile infrastructe can meet unexpected increases for example by increasing the number of EC2 instances by using Auto Scaling. 

_Elasticity_

Elastic and scalable infrastructure shares a common trait of increasing resouces based on demand. Only elastic infrastructure decreases as demand decresses. 

**Note:** See [Scalability and Elasticity](https://github.com/hamiltonrichard/CLF-CO2Notes/blob/main/AWSCertifiedCloudPractitionerStudyNotes.md#scalability-and-elasticity) in my Cloud Practitioner notes.

__Cost Management__

Compared to building up a data center, cloud computing has lower startup costs. Capital expenditures (CapEx) are greatly reduced since there is no need to purchase equipment up front. However, operational expenditures (Opex) increases.  You'll be billed for the cloud resources in smaller incremental ammounts. 

The cloud makes it easy to scale up or down depending on the demand for resources. This way you avoid the risk of either buying too much or not enough hardware.  

Over the long term, cloud computing may or may not save you money. Using [Pricing calculator](http://calculator.aws/#) you can help you determine the cost of cloud services. 

### The AWS Cloud

AWS offers a large number of services, but this table contains a list of the core services.

__Table 1.1__ AWS service categories
|Category|Function|
|:-------|:-------|
|Compute| These services replicate the role of physical servers. Advanced configurations such as autoscaling, load balancing,containers and serverless arhitectures are offered|
|Networking|Application connectivity, access control and enhanded connections |
|Storage| Various storage options designed for short and/or long term usage|
|Database| Various managed solutions utilize various formats including relational,No SQL or caching| 
|Application Management| Monitoring, auditing, and configuring AWS account services and running resources|
|Security and Identity|Services for managing, authentication and authoriation, data and connection encryption, and intergation with 3rd party authentication management systems|

__Table 1.2__ Core AWS Services by category
|__Category__|__Service__| Function|
|:------|:------|:------|
|Compute| Elastic Compute Cloud (EC2)|EC2 server instances provide virtual versions of the servers you would run in your local data center. EC2 instances can be provisioned with the CPU, memory, storage, and network interface profile to meet any application need, from a simple web server to one part of a cluster of instances, providing intergrated multi-tiered fleet architecture. Since EC2 instances are virtual, they're resource-efficent and deploy nearly instantly.
||Lambda| Serverless application architectures like the one provided by Amazon'e Lambda service allow you to provide responsive public-facing services without the need for a server that's actually running 24/7. Instead, network events (like consumer requests) can trigger the execution of a prdefined code-based operation. When the operation (which can currently run as long as 15 minutes) is complete, the Lambda event end, and all resources automatically shut down.|
||Auto Scaling| Copies of running EC2 instances can be defined as image templates and automatically launched (or scaled up)when client demand can't be met by existing instances. As demand drops, unused instances can be terminated (or scalled down.)|
||Elastic Load Balancing|Incoming network traffic can be directed between multiple web servers to ensure that a single web server isn't overwhelmed whild other servers are underused or that the traffice isn't directed to failed servers.|
||Elastic Container Service|Compute workloads using container technologies like Docker and Kubernetes can be provisions, automated, eployed and administered using full integration with your other AWS account resources. Kubernetes workloads have their own environment: Amazon Elastic Kubernetes Service (EKS).|
||Elastic Beanstalk|This is a managed service that abstracts the provisioning of AWS compute and networking infrastructure. You are required to do nothing more than push your application code, and Beanstalk automatically launches and manages all the necessary services in the background.|
|Networking|Virtual Private Cloud (VPC)|VPCs are highly configurable networking environments designed to host your ECS (and RDS) instances. You use VPC-based tools to secure and, if desired, isolate your instances by closely controlling inbound and outbound network access.|
||Direct Connect|By purchasing fast and secure network connections to AWS through a 3rd party provider, you can use Direct Connect to establish an enahanced direct tunnel between your local data center or office and your AWS-based VPCs.|
||Route 53|This is the AWS DNS server that let you manage, domain registraion, record administration, routing protocols, and health checks, which are fully intergrated with the rest of your AWS resources.|
||CloudFront|CloudFront is Amazon's distributed global content delivery network (CDN). When properly configured, a CloudFront distribution can store cached versions of your site's content at edge locations around the world so that they can delivered to customers on request with the greatest efficiency and lowest latency.|
|Storage|Simple Storage Service (S3)|S3 offers versatile, reliable, and inexpensive object storage that's great for data storage and backups. It's also commonly used as part of larger AWS production processes, including the storage of script, template. and log files|
||S3 Glacier|A good choice for when you need large data archives stored cheaply over the long term and can live with retrieval delays measuring in hours. Glacier's lifecycle management is closely intergrated with S3.|
||Elastic Block Storage (EBS)|EBS provides the persistent virtual storage drives that host the operating systems and working data of an EC2 instance. They're meant to mimic the function of the storage drives and partitions attached to physical servers.|
||Storage Gateway|Storage Gateway is a hybrid storage system that exposes AWS cloud storage as a local, on-premises applicance. Storage Gateway can be a great tool for migration and databackup and as part of disaster recovery operations.|
|Database|Relational Database Service(RDS)|RDS is a managed service that builds you a stable, escure, and reliable database instance. You can run a variety of SQL datbase engines on RDS, including MySQL, Microsoft SQL Server, Oracle and Amazon's own Aurora.|
||DynamoDB|DynamoDB can be used for fast, flexible, highly scalable, and managed nonrelational (NoSQL) database workloads.|
|Application management|CloudWatch||
||CloudFormation||
||CloudTrail||
||Config||
|Security and Identity|Identityand Access Management (IAM)||
||Key Management Service (KMS)||
||Directory Service||
|Application Intergration|Simple Notification Service (SNS)||
||Simple Workflow (SWF)||
||Simple Que Service(SQS)||
||API Gateway||


### AWS Platform Architecture
AWS has multiple datacenters across the globe that are grouped by [Region and Availablity zones](https://aws.amazon.com/about-aws/global-infrastructure/). Use cases for using different zones include:
* Customer Access
* Regularatory compliance

Because of low-latency access is so important,some services are offered from designated edge network locations. These services include CloudFront, Route 53, Firewall Manager, Shield and WAF. Refer to the AWS Documentation for [AWS Services by region](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/)

_Endpoint Information_

Enpoints in AWS use a specific naming formation:

__[protocol]:\[service-code\].\[region-code].amazonaws.com__

A description of the enpoint descriptions can be found in the [AWS Documentation](https://docs.aws.amazon.com/general/latest/gr/rande.html). 

### AWS Reliabilty and Compliance
__The AWS Shared Responsibilty Model__

__The AWS Service Level Agreement__

### Working with AWS
__AWS Organizations__

__AWS Control Tower__

__AWS Service Catalog__

__AWS License Manager__

__AWS Artifact__

__The AWS CLI__

__AWS SDKs__

__Technical Support and Online Resources__

__Support_Plans__

__Other Support_Resources__

### Migrating Existing Resources to AWS
__AWS Migration Hub__

__AWS Application Migration Service__

__AWS Application Discovery Service__


## Chapter 2 Compute Services

## Chapter 3 AWS Storage

## Chapter 4 Amazon Virtual Private Cloud VPC

## Chapter 5 Database Services

## Chapter 6 Authentication and Authorization - AWS Identity and Access Management

## Chapter 7 CloudTrail, Cloudwatch and AWS Config

## Chapter 8 The Domain Name System and Network Routing and Amazon Cloudfront

## Chapter 9 Data Ingestion, Transformation, and Analytics

## Chapter 10 Resilient Architectures

## Chapter 11 High-Performance Architectures

## Chapter 12 Secure Architectures

## Chapter 13 Cost-Optimized Architectures

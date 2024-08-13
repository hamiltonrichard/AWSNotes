# AWS Certified Cloud Practitioner Study Guide Notes - Foundational (CLF-C02 Exam) Second Edition

## __Introduction__

These notes were taken from the _AWS Certified Cloud Partitioner Study Guide_ book from Sybex written by Ben Piper and David Clinton. Feel free to use these notes, but check them for accuracy. 

## __Chapter 1 The Cloud__
### __What is Cloud Computing?__
Cloud computing allows you to run workloads in a secure enviornment utilzing the equipment of a cloud service provider. Cloud computing provides lower costs, more reliability and services that it would be hard to duplicate. 

__Highly Available and Scalable Resources__

A cloud environment can provide the following:

`*` Multiple layers of redundancy provide resiliency.

`*` Resources can be placed in different geographical regions. Allows for redistribution of resources in the case of a failure in one region.

`*` Assess to as much compute power as needed when needed. 

`*` Spend less for resources. 

__Professionally Secured Infrastructure__

As part of the Shared Responsibility model, AWS is responsible with the security of the infrastructure.  This allows users to focus on the configuration of the resources they use.

__Metered Payment Model__

In the cloud, you only pay for the resources you use. This reduces capital expences since there is no need to purchase hardware up front. 

### __Server virtualization: The Basics__

Virtualization allows the resources found in a powerful physical server to broken down in to what appears to be smaller servers. A hypervisor installed on the physical server is used to allocate memory and cpus to create what is seen as an EC2 instance.  Storage can also be allocation in a similar manner.

The advantages to this include:

`*` __Speed:__ Compute resources can be allowcated on the fly. This avoids the the hassles of having to purchase, install and configure a physical server.  Virtual servers respond faster to reboots and restarts. 

`*` __Efficiency:__ Virtualization can make better use of physical resources. Virtual servers can be assigned resources for a specific workload. Additional virtual servers can be allocated until all the physical server resources are used. 

### __Cloud Platform Models__

There are multiple cloud platform models to fulfill the needs of a particular project. The responsibilites of the user and provider vary.  These include:

__Infrastructure as a Service (IaaS)__

IaaS provides virtualized components that represent the physical compents you would utilize in an on premises environment. This would include virtual compute resources like EC2 instances that would replace physical hardware. Elastic Block Store (EBS) to handle data storage. The service provider is responsible for Virtualization, Networking and hardware. Applications,Databases, operating systems and their security are the responsibility of the user. 

__Platform as a Service (PaaS)__

PaaS allows you to focus on developing your applications and not the underlying infrastructure. AWS Elastic Beanstalk and Elastic Container Services (ECS) are examples of PaaS. In this offering, the user is responsible for their application.

__Software as a service SaaS__

SaaS provides access to applications. Examples include Gmail other Google applications. The responsibity for all of the compents falls on the service provider. 

The cloud platorm models provide different levels of responsibility unlike on premises deployments. 

### __Scalability and Elasticity__

Can providers though their vast physical hardware and resource virtualization they can provide scalability and elasticity. 

_Scalability_

Scalable services can automatically grow based on demand. This includes may services that AWS provides
 
_Elasticity_

Elastic services can grow and shrink automatically based on demand. "Elastic" services provided by AWS include:

[Elastic Load Balancer (ELB)](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/what-is-load-balancing.html) - This service will grow and shrink based on demand. 

[Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html) (ECS) - This service manages containers and can scale up or down as needed. 

[Elastic File System (EFS)](https://docs.aws.amazon.com/efs/latest/ug/whatisefs.html) - A scalable filesystem for Linux systems which allow you to add or remove storage as needed. 

Some AWS services do not have "Elastic" in their names, for example:

`*`[AWS Lambada](https://aws.amazon.com/lambda/) - This serverless computing service can scale up or down depending on the workload. 

The book suggests that "elastic" services allow you to configure minimum and maximum resources for a specific service. 

_Scalable, but not Elastic_ 

 Many services are scalable, but they all aren't considered "elastic". For example, Amazon EC2 is considered to be scalable since you can deploy instances instances manually. However, EC2 isn't "elastic" itself.  To deploy or destroy EC2 instances based on demand requires the use of AWS Auto Scaling. 


## __Chapter 2 Understanding Your AWS Account__
### __The Free Tier__
### __Product Pricing__
### __Service Limits__
### __Billing and Cost Management__

## __Chapter 3 Getting Support on AWS__
### __Support Plans__
### __Documentation and Online Help__
### __Trusted Advisor__

## __Chapter 4 Understand the AWS Environment__
### __AWS Global Infrastructure: AWS Regions__
### __AWS Global Infrastructure: Availability Zones__
### __AWS GLobal Infrastructure: Edge Locations__
### __AWS Global Infrastructure: Extending the Cloud__
### __The AWS Shared Responsibility Model__

## __Chapter 5 Securing Your AWS Resources__
## __Chapter 6 Working with Your AWS Resources__
## __Chapter 7 The Core Compute Services__
## __Chapter 8 The Core Storage Services__
## __Chapter 9 The Core Database Services__
## __Chapter 10 The Core Networking Services__
## __Chapter 11 Automating AWS Workloads__
## __Chapter 12 Common Use-Case Scenarios__

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

### Exam essentials.

* Understand how a large in geographically dispersed infrastructure improves service quality.

* Understand how metered, pay per use pricing makes for flexible compute options.

* Understand how serverless computing can be both cheap and efficient.

* Understand how scalability allows applications to grow to meet the deman.

* Understand how electricity matches compute power for both rising and falling demand.

### Summary

The size and quality of a major cloud provider. Like AWS means that is customers can often benefit from higher quality security availability and reliability than they can provide locally.

Well, AWS customers are still responsible for the applications they run in the cloud. They don't need to worry about the underlying physical infrastructure that's managed by AWS.

Much of the attraction of cloud computing is the ability to pay for only the services you need to use and only. When you use them?

Much of the attraction of cloud computing is the ability to pay for only the services you use, and only as you use them. This allows the provisioning of sophisticated applications with virtually no capital expenses. You will of course need to assess and manage the operating expenses.

Server visualization makes it possible to more densely packed software operations on fiscal hardware, potentially driving down the cost and approving the time to deployment of compute workloads. in even more virtualized kind of virtualizations is serverless computing, where customers are aware only of their code and the network events that trigger it. Cloud optimized workloads are designed to take advantage of scalability and elasticity of the cloud platform.

## __Chapter 2 Understanding Your AWS Account__

This chapter will show you the following:

* Taking advantage of the AWS Free Tier.
* Understanding how AWS services are priced and how to model pricing for complicated combinations (or stacks)  of resources.
* Understanding the usage limits AWS places on services and how to raise those limits.
* How to keep on top of your actual account costs.

### __The Free Tier__

Aws free tier services are offered for the first 12 months after opening an AWS account. This allows you to experiment with light versions of most aws services without being billed.

__How does the free tier work?__

An example of a free tier service is EC2. You are permitted to run AT 2 dot micro EC2 instance powder by Windows or Linux for up to 750 hours per month. You can also utilize S3 storage for up to 5 GIGS during the same year. If you exceed the free tier usage, you are only billed for the difference.

__Tracking your free tier Usage__

AWS will send you messages if you're free tier usage is approaching or has passed the limits. You can also check your billing dashboard.

__What's available under the free tier?__

The feature services include:

* Light implementations of most AWS service that are available for the first 12 months.
* light usage of certain aws services that are always available even after your initial 12 months are up.

You can get a detailed rundown of both classes or services at https://aws.amazon.com/free.
### __Product Pricing__

You can find out about pricing by going to the pages for Amazon services. For example, if you go to [the S3 product page](https://aws.amazon.com/s3/) you can click on [pricing](https://aws.amazon.com/s3/pricing/?nc=sn&loc=4) to get the details.


### Working with the AWS Pricing Calculator

You can use the AWS pricing calculator to create estimates it allows you to select the services and configure them and show what the cost that you occur.

The calculator has two benefits:

1. The pricing is up to date so you'll be confident you'll get an accurate picture of your real cost.

2. The final review is an excellent way to visualize the impact of each individual element you will have On your overall budget it's also easy to modify the configuration so you can come up with multiples so you can see what the cost involved would be for each.

#### __Exercise 2.1__

[Create an estimate using the AWS Cost calculator.](https://docs.aws.amazon.com/pricing-calculator/latest/userguide/generate-estimate.html)

### __Service Limits__

AWS does impose service limits. most of the limits are soft. This means you can request an increase. However, there are some hard limits that can't be increased.

You can find a complete and updated list of service limits on the AWS documentation page https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html



### __Billing and Cost Management__

Along with keeping track of performance, you'll want to keep an eye on the expenses using the billing dashboard. Various tools can be found in the building dashboard to help with your account oversight. The dashboard  is accessible through the account dropped down menu at the top of the AWS management console. https://console.aws.amazon.com/console.

__The AWS Billing Dashboard__

The billing and cost management dashboard contains several visual spin summaries that display your cost. For the previous or current months so far, along with the forecast of the costs, you'll likely to face at the end of the month. Links are also included to set. up your payment information and enter. your organization tax information. The payments leak provides records for previous transactions.

__AWS Budgets__

AWS Budgets is a tool that can track a specified series of events and send alerts if a threshold is close to being reached or has exceded budget specifications. 

You can create the following budget types.

* cost budgets to monitor the cost of preset service. Being incurred almost your account using either fixed or variable targets.

* Uses budgets to track how much of a particular service you consume

* Reservation instance utilization or coverage budgets to help you understand how close your actual usage is to matching reserve instances you've purchased.

* saving plans coverage budgets to help understand how close you are to your actual uses to match the saving plans you've purchased.


### __Monitoring Your Costs__

__Cost Explorer__

Let you build graphs to visualize your accounts historical and current cost the default view shows you're spending over the past few months broke it down by service. You can configure the parameters letting your filter account cost by events, by date range, region, availability zone, service instance type and others. ___Formated CSV files can be downloaded which contains based on the customized views provided.___

Cost Explorer can be found at https://aws.amaon.com/aws-cost-management

[Analyzing your costs and usage with AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html)

__Cost and Usage Reports__

Cost and usage reports are accessed from the porch link on the building dashboard. you can configure reports to be created that include the full range of activity on your account including what resources you have been running and how much they're costing you You can control the level of detail and able support for Redshift and or Amazon Quicksite (A manage pay per user business intelligence tool). The reports are generated at Preset and are compressed saved using a csv format and then sent to an S3 bucket you've already created. you'll need to configure Redshift or QuickSight to access In process the data it generated.

[How to create a cost and usage dashboard](https://docs.aws.amazon.com/cur/latest/userguide/dataexports-create-dashboard.html)

__Cost Allocation Tags__

tags are metadata information elements representing a resource and its actions tasks can be used organized and track your resources allowing you to visualize and better understand how resources are being used chesty confused things however aws offers two distinct kinds of tags that actually have nothing to do with each other.

__Cost allocation tags__ are meant to interact with the billing tools and won't show up in any context of any other aws resource process. They are solely for the purpose of tracking your account spending.

AWS also provides __resource tags__.these tags help administrators identify different resources.

### __AWS Organizations__

Formally known as consolidated billing, idiots organizations allow you to centralize the administration of multiple AWS accounts owned or controlled by a single company. 

Remember that once accounts are linked maintain a secure profile and following best practices becomes even more critical than for stand alone accounts after all a security breach in any one length account runs the wrist of spreading the vulnerability to everything running in any of your accounts.

### Summary

tier offers new accounts a full year of free access to light configuration of most aw services It's meant to be an opportunity to experiment and learn with your organizational needs in the cloud.

AWS pricing calculator led you anticipate real-world uses costs for AWS deployments.

Remember that resource request can be refused if your request would have passed your consumption past a define service limit. Some services can be increased And have soft limits while others are fixed having hard limits.

ADBS Billing Dashboards that hub for accessing account information, payment and tax status, management cost, monitoring and cost control

### Exam Essentials

* I understand the value of the 12 months free tier. The free tier lets you run light services such as AT 2 micro EC2 instance and a 30 gig ebs volume. the goal is to get you comfortable with aws services so you can learn how they can be used to host your applications.

* I understand the value of permanent free services. Low volume consumption includes the retrieval of up to one million free AWS Lombarda request or 62,000 outbound emails through Amazon scs each month.

* Know how to access Amazon's resource pricing documentation.

* Used aws pricing calculator to accurately model multitiered application stack pricing.

* Understand how to use AWS services is limited by default. some restrictions are hard Restrictions meaning that they are fixed and cannot be changed. other restrictions are soft ones and can be changed if requested. 

*Understand the value of cost management tools for avoiding costly cloud overspends. AWS budgets can be configured to send alerts when your resource consumption approaches or passes a preset limit. cost and usage reports can send you in depth and ongoing CSV/ formatted data to Redshift or QuickSite for analysis you can use cost allocation tags to more effectively track and manage source of your account cost the security operations of multiple AWS accounts is controlled by single company can be managed through AWS organizations.
## __Chapter 3 Getting Support on AWS__
### __Support Plans__
When you create a new aws account, you're required to select a support plan.

Types of support plans and their costs.

|__AWS Service Plan__ | __Cost of Plan__ | __Additional Notes__|                           
| :---:| :---|:---|
| _Developer Plan_ | <ul><li>$29 a month or</li><li>3% of your monthly account usage.</li></ul>|This plan is suitable for non production workloads. Limitations of the plan include access to support staff, which is only available during business hours via email.This also gets you limited access to the trusted advisor tool.|
|_Business Plan_| <ul><li>Greater of $100 or</li><li>10% of usage up to $10.000</li><li>7% of usage up to $80,000</li><li>5% usage up to $250,000</li><li>3% of usage over $250,000</li></ul>|This plan includes support for down resources. This plan guarantees a response from a cloud engineer via email chat or phone call within one hour. Less severe issues can take longer up to 24 hours. This circle can include help troubleshooting. Interprobability between Advs Resources and 3rd party software and operating systems. For the additional fee, you can also get in depth guidance while your. Still in the project design stage through infrastructure, event management.|
|_Enterprise Plan_|<ul><li>Greator of $15,000 or</li><li>10% of AWS usage for the first $150,000</li><li>7% of AWS usage from $150,000-$500,000</li><li>7% of AWS usage from $150,000 - $500,000</li><li>5% of AWS usage from $500,000 - $1,000,000</li><li>3% of usage over $1,000,000</li></ul>|This plan is appropriate only for large organizations. The scope is global and for whom downtime is unacceptable. You get a technical account manager assigned to you for guidance advocacy. A technical account manager becomes closely involved with your deployment, guides your team through planning launches and proactive reviews and all optimize using best practices. In addition to technical account managers, you get 24/7 access to senior support cloud engineers and a 15 minute response time for business critical troubleshooting.|

Check for updated [Support Plan Pricing here](https://aws.amazon.com/premiumsupport/pricing/).

There is also an Enterprise On-Ramp support level for business critical workloads that will cost greater of $5500 or 10 per cent of your annual AWS usage.

Beyond those support resources, all paid support plans come with prioritized access to [AWS re:Post](https://repost.aws/knowledge-center/all).

### AWS Professional Services.

Support is also available through the AWS professional services organization. The team provides offerings which are detailed guys to achieving specific outcomes and work with third-party consultants from the AWS Partner network to actively help you build your deployments. The services team also makes tech talk webinars, white papers and post. and posts publicly available.

### __Documentation and Online Help__

__AWS Documentation__

The AWS Documentation can be found or the [documentation site](https://docs.aws.amazon.com/). When looking for documenation, make sure the URL contains _latest_. 

An important subset of the documentation is the [AWS Prescriptive Guidance Library](https://aws.amazon.com/prescriptive-guidance). You'll find a collection of papers from AWS exports. 

__Knowledge Center__

The [AWS Knowledge Center](https://repost.aws/knowledge-center) is basically a FAQ page with items sorted by service. 

__Security Resources__

Amazon Security oriented sites:

* [Cloud Security Learning Resources](https://aws.amazon.com/security/security-learning/?cards-top.sort-by=item.additionalFields.sortDate&cards-top.sort-order=desc&awsf.Types=*all).
* [AWS Security Blog](https://aws.amazon.com/blogs/security/)
*

### __Trusted Advisor__

Trusted Advisor can be used to confirm whether your account resource configurations are sound and are compliant with best practices. There are five catagories:

|Catagory|Purpose|Examples|
|---|---|---|
|Cost Optimization| Identify any resources that are running and costing money that are underutilized or inactive| EC2 Instances or Redshift clusters that, overtime, are idle.|
Performance| Identifies configuration settings that might be blocking performance improviements.| Inappropriate reliance on slower magnetic or low-throughput EBS volumes.|
|Security| Identifies any failures to use security best-practice configurations| S3 buckets with publically accessable permissions or security groups permitting unrestricted access|
|Fault Tolerance| Identifies any running resources that, through poor configuration, are unnecessarily vunerable to service disruptions|Data volumes that aren't properly backed up or instances that aren't replicated.|
|Service Limits| Identifies resource usage that's approaching AWS REgion or service limits.|Your account is currently using close to the 100 S3 bucket limit|

### __Exam Essentials__

**Know how to choose a support plan that reflects your operational needs.** Configuration mistakes can be costly. Better support levels have their advantages. 

**Understand the benefits of the Enterprise Supoort plan's technical account manager.**  Having a TAM can make a significant differents in the quality of service. 

**Understand how to find AWS resource usage through the offical AWS documentation.** Remeber there is resource documentation and also the [Knowledge Center](https://repost.aws/knowledge-center). 

**Understand how to use the Trusted Advisor for alerts to common system misconfigurations.**  Routinely visit the Trusted Advisor to ensure that your resource configurations are sound and compliant with best practices. 


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

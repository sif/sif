---
layout: post
title: "Amazon Web Services I"
categories: cloud
tags: cloud cloud_computing AWS
---

* TOC
{:toc}

## Foundation

Products and Services, AWS Partner Network, Marketplace

What do you need to know to pass the Certified Solutions Architect Associate Exam?
Messaging, Desktop & App Streaming, Security & Identity, Management Tools, Storage, Databases, Networking & Content Delivery, Compute, AWS Global Infrastructure

Easy
1. Developer Associate
2. Solutions Architect Associate
3. Sysops Administrator Associate
4. Security Specialty
5. Big Data Specialty
6. Devops Pro
7. Advanced Networking Specialty
8. Solutions Architect Professional
Hard

| Partner | Associate Certs | Professional Certs |
| --- | --- | --- |
| Standard | 2 | 0 |
| Advanced | 4 | 2 |
| Premier | 20 | 8 |

Domain 1: Design Secure Architectures 30% 
Domain 2: Design Resilient Architectures 26% 
Domain 3: Design High-Performing Architectures 24%
Domain 4: Design Cost-Optimized Architectures 20%

Which statement best describes a Region?
A physical location around the world comprised of multiple, isolated, and physically separate Availability Zones within a geographic area.

Which one of the following items is NOT managed by AWS, according to the shared responsibility model?
Customer data

Geographic Regions (22)
choosing a region depends on compliance, proximity, available services, and pricing

Availability Zones (69)

AZ forms regions

Data centers

point of presence - Edge Location are data centers that are owned by a trusted partner of AWS

some services are based on regions and some are global

transaction per second (TPS)
average rate (AvgRT)

The 6 Pillars of the AWS Well-Architected Framework

1. Operational excellence
2. Security
3. Reliability
4. Performance efficiency
5. Cost optimization
6. Sustainability

Well-Architected Infrastructure

* Reliable
* Fault tolerance
* High availability
* Durability
* Secure
* Performant
* Cost-effective
* Operationally excellent
* Monitored
* Automated
* Effective processes

make reversible changes
perform business as operations as code
anticipate failures
learn from operational failures
Shared Responsibility Model
apply security at all layers
automate security best practices
keep people away from data
automatically recover from failure
test recovery procedures
implement Cloud Financial Management
adopt a Consumption Model

AWS is responsible for "security of the cloud"
Customer is responsible for the "security in the cloud"

Scale cube

Three-Tier Architecture

- Load Balancing tier
- Application tier
- Database tier

* Internet access
* Isolation & security
* High-Availability



## Security, Identity & Compliance



### IAM

What is the single best thing you can do to secure the root account in AWS?
Enable multi-factor authentication (MFA).

Why is it dangerous to use the AWS root user account?
The root user account has full permissions to every service.

Identity and Access Management
A global service

Users and groups
Permissions, can be assigned JSON documents called policies
Principle of least privilege

Policies
best to apply policies to groups rather than users, so that users can just inherit permissions from groups

MFA

IAM Policy Documents -> Group -> Users
Policy Documents are in JSON

You use usernames and passwords to log into the console but you use access key ID and secret access keys to use AWS via API and command line

explicit deny, a deny that will override any allow policy



### SCIM (System for Cross-domain Identity Management)



### Shield Advanced

- protect AWS resource that is internet-facing
- enable layer 7 protection for CloudFlare and ALB resources by associating an AWS WAF
- configure AWS WAF Rate Based Rules
- configure proactive engagement to receive direct contact from AWS Shield Response Team (SRT)
- configure CloudWatch alarms for Shield and WAF to receive notificcations when you are under attack



## Compute



### Lambda

pure serverless solution

compute service
function as a service
useful for API hosting, event processing, etc.

- no server to manage
- autoscaling
- pay as you go
- performance
- service integration
- focus on code

cold start is an issue with serverless solutions (functions and containers) in general

the main issue is latency, so find a way to keep it warm



### Elastic Compute Cloud (EC2)

https://stackoverflow.com/questions/17161345/how-to-open-a-web-server-port-on-ec2-instance



Which statement best defines Amazon EC2?
It is a service that provides secure, resizable compute capacity in the cloud.

What is the purpose of an Amazon Machine Image (AMI)?
It's a template to create a new EC2 instance from.

When deploying an EC2 instance, where is the instance deployed by default?
The default VPC

How many instances can run in a single Availability Zone for a spread placement group?
7



elastic compute cloud, provision server on demand



Nitro
vCPU



### 



ECS – elastic container service, Docker service


## Cloud Development Kit (CDK)

- https://cdkworkshop.com
- https://cdkpatterns.com
- https://constructs.dev

open-source
enables writing imperative code to generate declarative CloudFormation templates

CDK -> CloudFormation -> AWS (CDK does not create the actual resources itself)

Alternatively: CDK -> Terraform -> AWS

the root of CDK is the CDK app

  * App: no CloudFormation equivalent, App is a special root Construct, orchestrates the lifecycle of the Stacks and Resources within it
  * Stack: CloudFormation Stack
    * Nested Stack: CloudFormation Nested Stack
    * Construct: 1 (or more) CloudFormation Resources

can have multiple Apps, Apps can have multiple Stacks

the output of CDK is CloudFormation

App lifecycle: Construct -> Prepare -> Validate -> Synthesize -> Deploy

CDK Constructs: 

- Level 0: Basic Resource (no Type)
- Level 1: CloudFormation Resource (1:1), prefixed with Cfn (CloudFormation)
- Level 2: Improved L1
- Level 3: Combinations of Constructs

`cdk synth` generates the CloudFormation Template by traversing the App tree and invokes the synthesize method on all constructs then generates unique IDs for Cfn resources

Assets are files bundled into CDK apps such as Lambda Handler Code, Docker Images, etc.

Assets can represent any artifact that the app needs to operate

When synthesize or deploy a CDK, these typically end up in `cdk.out`

`cdk bootstrap' creates a S3 Bucket to store Assets, required for Assets and Cfn templates greater than 50 kB

Methods of all Constructs are called in series: prepare, validate, synthesize



CDK Pipelines - useful for CD/CI



### CloudFormation

lets you provision AWS Resources in Stacks

AWS Resources is anything that AWS offers (Lambda, S3, etc.)

A Stack is a collection of AWS Resources

Stack Templates are in YAML/JSON format and are declarative code

 

### CodeDeploy



## Storage



### Simple Storage Service (S3)

Since S3 is an object-based storage solution, which type of file should never be stored in it?
Operating system's boot files

Why is versioning not enabled by default on new S3 buckets?
It costs money, as you'll be paying for every additional copy of objects that you upload.

One of the oldest service

Buckets, name is universal so good names are hard to come by

How the bucket URL is formed:

```
https://bucket-name.s3.Region.amazonaws.com/key-name
```

Key-Value Store, typically the key is the name of the file

Will also have version ID (different versions of the same object), metadata

Availability and durability, 99.99% availability and 99.99999999999% durability (11 9s)

Data is stored in multiple facilities (>=3 AZs)

Designed for frequent access

Security, Server-Side Encryption, ACLs, Bucket Policies

Consistenty Model, Strong Read-After-Write Consistency

Zero Disk Architecture - instead of writing to a storage server, write to S3; this way no management of storage server, all offloaded to AWS; useful if latency not a concern



### Elastic Block Store (EBS)



## Glacier



###

EFS - Elastic File System

Amazon EFS is designed to provide massively parallel shared access to thousands of Amazon EC2 instances.

Glacier allows you to store single object in region distribution



## Application Services



### 

SNS – simple notification service

SES – simple email service

SQS – simple queue service



## Databases

Cassandra/Mongo (on EC2)



### Relational Database Service (RDS)

What should you do to scale out an RDS database that has a read-heavy workload?
Add additional read replicas



### DynamoDB

NoSQL 



### ElastiCache



### Aurora

Amazon Aurora is fully compatible with which of the following database engines?
MySQL



## Analytics

Kinesis

Elasticsearch Service

Redshift

EMR – Hadoop framework, ETL, big data use

Athena – analytics with SQL



### Glue UI



## Networking

AWS will start charging $4/month for IPv4 addresses

Biggest challenge in adopting IPv6 is ISP support and support for developer tools



### Virtual Private Cloud (VPC)

- Logically isolated network
  - Created per Account per Region
  - Spans a single region
  - Can use all AZs within one Region
  - Can peer with other VPCs
  - Internet and VPN gateways
  - Numerous security mechanism
  - 5 VPC per Region (soft limit)

When you create a VPC, you must specify a range of IPv4 addresses for the VPC in the form of a Classless Inter-Domain Routing (CIDR)

Subsets

- Security via isolation
- High-Availability
- Fault-Tolerance
- Performance

Create VPC, then create a subnet, then launch an EC2 inside the subnet

Create IGW (internet gateway) to allow communication between subnet and outside world, do so by attaching IGW to VPC (Directory Gateway)

Then create a route table

For database, create a new (private) subnet which will not have access to the IGW, then stick the database in the subnet

Multi-availability strategy for high availability

Create 2 new subnet, one private and public

Setup load balancer via Elastic Load Balancer (ELB)

Virtual private gateway (VPG) is an option



## Routing

Network access control lists

Security groups

Development/Deployment

CodeCommit (deprecated)

CodeDeploy

CodeBuild

CodePipeline

OpsWorks



### Elastic Kubernetes Service (EKS)



Lightsail – for simple virtual private server solution

CloudWatch Alarms



## Console



## Cloud9

Cloud IDE



## Elastic Load Balancing (ELB)

Which AWS service would you select to distribute web traffic between web-facing EC2 instances?
Elastic Load Balancers



## Elastic Beanstalk

For deploying webapps
Test or development, not recommended for production



### Web Environment

**Single-Instance Env**

Launches a single EC2 instance, an EIP is assigned to the EC2



**Load Balanced Env**

Launches EC2s behind an ELB managed by an ASG



### Worker Environment

Creates a SQS queue, install the SQS daemon on the EC2 instances, and has ASG scaling policy which will add or remove instances based on the queue size



### Deployment Policy

In-Place deployment is when deployment occurs within the environment, all deployment policies are In-Place.

**All at once**



**Rolling**

Rolling deployment polices require an ELB so cannot be used with Single-Instance Web Environments.



**Rolling with additional batch**



**Immutable**



**Blue/Green**



## Cognito



https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-app-ui-customization.html



## Route 53

DNS

What is the purpose of DNS?
DNS allows you to assign something that's easy to remember to an IP address (e.g., example.com —> 1.2.3.4).

What is the Route 53 service?
A service by AWS that allows you to route domain names using DNS.

What is a Route 53 health check?
It's a test that allows you to determine if your endpoint is online.



## Secrets Manager



NAT gateways vs NAT instances



## Management and Governance

### Systems Manager

SSM



### Amazon CloudWatch

Which tool would you use to monitor the CPU usage of an EC2 instance?
CloudWatch

CloudWatch Events now part of EventBridge



## Vocabulary

ARN Amazon Resource Name



KMS Key Management Service



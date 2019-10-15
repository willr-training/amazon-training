To watch again:
https://onlinexperiences.com/launch/UUID.htm?ShowKey=72114&LocaleID=1033&UUID=D473E317-9C43-4A71-B8E7-BD0E32340F9A

Session: Introductory guide to AWS cost management and efficiency

Link: https://mktg-apac.s3-ap-southeast-1.amazonaws.com/FY19Q3+Builders+Online+Series/AWS+Cloud+Economics+Journey+-+Introductory+Guide+2019.pdf

Agenda

- The economics of aws
- Using aws in a cost efficent way


## Economics

Cloud revolution -> shift to on-demand computing

Problems old model
- create/maintain hardware
- problem with upgrade
- pb respond to cust needs
- upfront invest in hardware

Eliminate waste
- traditional hardware spend misses business demand peak

Other benefits
- cost savings
- staff productivity
- operational resiliency
- business agility -> innovation


# Using aws in cost optimised way

[image]

- right size & decomission unused resource


## Right size

[image]

Picking the right instance size

- accelerated computing (AI, ML)
- storage optmised

Size can be prior or after deployment.

[image]

Navigate: aws cost explorer
- instances and cost of resources

Check: AWS Trusted advisor (business support)

## Turn off resources

[image]

AWS AWS Instance Scheduller

Third party tools:
Gorilla Stack
Skeddly
ParkMyCloud

What are RIs (Reserved Instance)?

[image]

- used for always-on instances
- mostly used for some tools

[image]

EC2 RI types

What are convertible RIs? And their features?

[image]

What happens when you exchange a convertible RI?

[image]

Another feature: Instance size flexibilty

How to know which RI type to used?

Check: AWS cost explorer

[image]

## Design for cost

Several methods
[image]

# How to manage your spend

- estimate spend for expectations
- measuring/monitorung spend
- metrics to know how efficent is spend

Considering optimisation

[image]

On-premises cost vs AWS

Several levers of reduction
[image]

## To measure spend, use Cost explorer

[image]

AWS Budgets
- set warnings against Budgets

## Metrics to measure spend efficiency

[image]

Summary of this session: [link in session]

Other free training resources
[image]

--------------------------------------------------------------------------------
Session: Scale serverless app (Amplify)
Building serverless applications that scale on aws

Agenda
what we mean serverless

# What is serverless

- no infra provisioning/management
- auto scaling (no problem with CPUs..)
- pay for value (only for time code is executed you're billed) e.g. Lambdas
- highly available and secure (by design)

Serverless is composed of many services

- compute: aws lambda, aws fargate
- data stores: dynamoDB (NoSQL), Aurora, S3
- integration: API gateway, SQS, SNS (pub sub messaging), Step functions (processflow of Lambda functions), AppSync (graphql)

[image]

As developer I want...

- support for multi platform and framework
- code generation to eliminate boilerplate

[image]

Amplify framework: Lib, UI components, CLI

- Libraries = SDKs

[image]

A few simple tasks when building an application

### Authentication

Add auth with amplify (terminal)

`amplify add auth`
`amplify push`

In the background Cloudformation does ...

Add auth with JS front end

import amplify from 'aws-amplify'
import awsmobile from `./aws-exports`
import

[image]

Very few lines of code to get auth in the application. Very cool!

How does the auth work - Amazon Cognito

[image]

- client authenticates
- client receives short term credentials
- cleint interacts with other aws services using credentials

### API & Data stores

[image]

Adding a graphql + NoSQL Backend with Amplify

`amplify add api`
`amplify push`

[image]

type Todo @model {
id: ID!
description:String!
completed: Boolean!
}

amplify uses `nested stacks`

Scoping Data Per-User -->> nice feature


How does graphql work with AppSync?

[image]

Amplify graphql Transforms

[image]

### CI/CD & Hosting

- set up builds and deployment per branch
- ...

AWS Amplify Console

[image]

Config CI/CD & Hosting with Amplify

[image]

### Review

- Amplify: simplify provisioning/config cloud resources
- Cognito: add user Authentication and authorisation
-

Further reading;
[image]

-----------------------------------------------------------------

Next session: Security
Move fast and be secure on AWS cloud

- outsourced dev
- lean start up (test and fail fast)
- low costs

Think about security
- for users
- for providers
- for us

Security culture
- Security is everyone's job == features
- Secure = complete

Security considerations
- secure env
- separation of duties
- monitoring
--> All contribute to Secure application

Secure env
- Multi-factor Authentication
-- digital or physical token
- Dont use root account (one per user)
- Federate identity
- Federate identity
- Least priviledge
- Disable public buckets (no public S3)

Separation of duties: diff account for different users
- multi-account strategy
- sandbox : trial aws before launch
Core
- security account
- shared services
application
- Test/Prod

Monitoring

- AWS CloudTrail: who did what, what was done, what services touched
- AWS GuardDuty:

[image]

Automating remediation: GuardDuty available on CloudWatch

AWS Config : state of env, how changes over time, create alert

Dashboard
AWS Security Hub -> all checks seen in one hub
[image]

Monitoring revolution
Manual -> alerting (e.g. slack) -> automated

Secure application = use service features
[image]

AWS CloudFront
Load Balancer
AWS EC2
AWS providers
AWS Certificate manager: ssl certificates (data in transit)
AWS KMS: data security at rest

Easy steps to Security
[image]

Security mechanisms = completed
[image]

What is the cost of all this? 16$/month
[image]

Other reading:
well-architected framework
aws security best practices - whitepapers

Other courses:
[image]

-----------------------------------------------------------------------------

Next session: Databases
Choosing Databases for serverless architecture

Agenda
Aurora
RDS

# Monolith to Serverless

From monolithic app to microservices
- teams understand code/manage code

[image]

Microservice architecture

[image]

- 1 microservices = 1 database (rule of thumb)

What is Serverless
[image]

# Aurora (relational)

- availability nodes
- 1 master node
- reader nodes

Choices to make
Provision for peak or provision less peak or continuous monitoring

What aurora does
- scale capacity (no down)
[image]

How does it work?

- monitoring services
- warm-pool aurora instances
- multi-tenant proxy layer (HA proxy)

DB scales up and down

[image]

If no activity (dev workloads), instances can scale down without loss of data (in storage)

Other features of Aurora

[image]

# AWS RDS Data api

- connection between application and database
- use typical microservices call

[image]

Aurora serverless availability
- PostGreSQL
- MySQL (most regions)

# Amazon DynamoDB (no relational)

- infinite scalability
- serverless
- enterprise ready (ACID, encryption rest, on demand backup)

[iamge]

## Performance at scale
- consistent low latency (1 milisecond variance)
- start with DynamoDB for your applications! Better than relational

Why is it important
- amazon reduced costs and maintenance

## Serveerless
[iamge]

- Security
- durability
- availability
- Performance
- scalability

Auto scaling for DynamoDB (recent)
- auto scale policies

Read/write capacity on-demand
- no capacity planning

Why is it important for customers?
[image]
- reduce risk
- reduce costs
- move faster

## Enterprise ready

Why is it important
- unlock innovation
- move faster
- reduce risk
- eliminate versioning (no upgrades)

[image]

# Summary
[image]

monolithic > microservices
servers > containers/Serverless
databases > serverless capabilities

----------------------------------------------------------------------------

Next session: Build CD/CI pipeline
Set up a serverless app with a full CI/CD pipeline in minutes

3 Pilars of software development

EC2 = virtual private servers

Run phase
[image]
- Compute
- Storage & Databases
- 100+ services

Release phase
AWS CodeStar
[iamge]

Relase: AWS Code Services
Source
- aws codecommit
Build
- AWS CodeBuild (CI service on cloud). Pre config tests.
Test
- Third party tools (jenkins etc)
Deploy
- AWS CodeDeploy (no downtime)

All services can work independently. Otherwise, can use **AWS CodePipeline**

AWS CodeStar
- CI/CD pipeline all setup

AWS CodeStar
[image]

Create phase
AWS Cloud9
- Fully feature identity
- Just web browser

AWS code tools
[iamge]

Start new projects
[iamge]

AWS Cloud9
- code together in realtime
- little config and installation

---------------------------------------------------------------

Next session: Migration to aws
Migrate your unstructured data to AWS in just a few clicks »

Agenda
Why move data to aws
Where in aws
How to move data to aws
What can I do when it's there
Example/demo

# Why move data to AWS

Amount of data increasing
[image]

Where is data stored on premises

File servers
NAS (paralell file systems)

## Considerations before moving to aws
- Why move data Storage (realtime data need..)
- What is the data being moved (realtime, home directory..)
- Where is data going to (service/app/use case)
- How much data

## Why move from on-premise
[image]

# Where should data be moved
- broad storage portfolio
[image]

file storage
obj Storage
block Storage
backup
hybrid
transport and edge

## Amazon S3
[image]

- various storage classes (standard, standard-ia)
- data management
- access management
- cross region replication
...

## File Storage e.g. home directories etc
Amazon FSX
Amazon FSX for Luster [image] works with S3 (persistance)
Amazon Elastic FileSystem e.g.linux based workloads
[iamge]

Demo FSx for windows

# How to move to aws?

What type of transfer required:
- offline
- hybrid
- on premises
[iamge]

Storage gateway
[image]

File gateway
[iamge]

Volume gateway
[image]

Tape gateway
[iamge]

Snowball edge - most offline migration
[image]

AWS for SFTP (manage sftp service)
- network interface
- maintain Storage (ingest/take data out)

## Summary - how to make a Choices
[image]

Example of moving data to aws

# Introduction to AWS

## General introduction

DevOps definition
- software dev
- IT ops
- shorten system dev life cycle

What is cloud computing
- on demand compute (db storage, apps, other IT)
- pay as you go
- right size 

Types of cloud computing
- IaaS
- PaaS
- SaaS

> Docker between IaaS and PaaS

Advantages of cloud
- CapEx vs OpEx
- no CapEx with Cloud
- Economies of scale > HA and Fault tolerance
- Good community for Q&As
- Stop guessing capacity required
- Speed to go global
- Great functionality out of box

Cons
- No: just move existing on-premise infra to cloud


## Lab 1

- sign up aws
- create budget

## Regions and AZs

- Regions = physical locations
- AZ = datacenters within regions
- webservices: `protocol://service-code.region-code.amazonaws.com`

Compliance and data residency
- data ownership where you have region 
- data residency requirements

Hosting
- monolithic approach

[images]

Services in AWS
- mix of IaaS, PaaS and SaaS
- low level and high level resources
- Automation to configure provision of service ==> cli interface

> AWS is no magic. Servers are deployed by amazon.

## Lab 

- Create first AWS instance

ap-southeast-2
ec2-52-65-204-133.ap-southeast-2.compute.amazonaws.com
52.65.204.133

- launched ec2 instance

[image]

## Security

Shared security responsibility model
- AWS
    - global infrastructure
    - security config of products for `managed services`

- Client responsibility
    - IaaS completely under your control
    - user IAM utilities

Network isolation
- vpn: isolated network = virtual network
- subnet: range of ip addresses in VPC

Isolation on physical hosts
- ec2 instances 
- termination of instances scrubs memory

Root user credentials
- signup user = root user
- best practice = create a separate user

IAM 

## Lab3 - create IAM user

^2qZYxp9yw
AKIASS34X6VCEQ3EN222

## IAM

Policy to: 
- Identity
- Resource

Identity to: 
- Users/groups ==> people
- roles ==> machines

Practices:
- never share user
- user groups to group similar patterns

## Elasticity

- EC2
- scalable computing 
- removes need for hardware
- dev and deploy faster
- instances = virtual computing env

EC2 instance types

- 5 instance types (compute, memory, graphics, storage)
- limits: vCPUs per region
- many different

[image]

What is vCPU?
- T2 instance = CPU Core ==> physical core
- non T2 instances = hyper-thread of a physical core ==> logical core
- 0.5vCPU to 96 vCPU per instance

Purchase options
[image]

Pricing depends
- no one fits all
- instance type
- type of rental
- OS
- region

Strategies 
- combine on-demand and spot instances

## AMI

AMI = virtual machine on instance

[image]

User-Data
- config instance when launched. Opposed to 

## Lab 4 User-Data

ec2-13-211-105-57.ap-southeast-2.compute.amazonaws.com

13.211.105.57

## Lab 5

## Scalability

Vertical scaling 
- requirement 10k per day
- requirement 10k per hour
- requirement 10k per min

Elasticity + Scalability
- Horizontal vs Vertical scaling 

## Lab 6

goal: create autoscaling group and attach to load balancer

## Auto scaling group

automatica scaling for aws resources
uses ec2 + cloudwatch princing 
ec2 auto scaling groups
amazon ecs
use manual or auto scaling 

Launch template

- config to launch an instance
- one or more launch template versions

Load Balancer
- distribte income app or network traffic across multiple targets

Why load balancing
- across multiple instances ==> increase HA and fault tolerance
- add/remove compute resources w/o interuption
- offload the work of encryption and decryption to load bal
- separate pub and pr subnets

Health checks
- need to check health targets

Classic Load Balancer (version 1 - no longer recommended)

Application Load Balancer
- Layer 7 load balancer http layer
- content based routing 
- for microservices and containerised apps

Network Load Balancer
- very high throughput 
- layer 4 OSI

Target group
- every LB needs it 
- groups targets together



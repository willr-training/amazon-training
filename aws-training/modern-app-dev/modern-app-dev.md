# Modern application design

Goals:
1. Business case
2. Architectural Patterns
3. Operating model
4. Software delivery

## Business case

- driven by client use cases
- innovation flywheel
  + do something small
  + scale little by little (experiment)

[image]

### What defines modern apps

- microservices architecture
- containers/serverless

[image]

## Architectural Patterns

- Monolith vs microservices
  + start with Monolith to understand business problem
  + shared logging
  + shared interface
  + single deployment ...

[image]

- microservices
    + datastore by microservice
    + custom interface > specific functionality by interface
    + logging by microservice > non standard
    + own deployment logic > diff by team

[image]

### Architectural choices

- Monolith: UI + Business logic + data access layer = all together

[image x 2]

API gatheway: consolidate access patterns for external API consumption
Microservice does not have to have a public API

[image]

### Evolution of computing

- Physical servers
- Virtual servers > physical limits
- Virtual servers in cloud > cloud computing
  + high utilisation
  + faster provision
  + DR
  + improved uptime
  + hardware independence

- Cons:
  + from OPEX to CAPEX
  + scale
  + elastic resources

[image x 2]

### Containers
immutable obj contains code, runtime, dependencies...

[image]

- excellent for stateless application
- great for local testing

### Evolving to serverless

aws lambda: function as a service.
+ run code at 1000x/sec
SNS: notification
Step functions: state manager (e.g.manage the state of accounts)
SQS: queue services

[image]

APIs are front door to microservices
- api is clean
- self explanatory APIs (intuitive)

API Gateways

amazon cloudfront: content delivery network
API cache: check if recent call/data
amazon cloudwatch

[image]

### Event driven architectures

> messaging patterns
- queues in btw microservices to prevent coupling microservices
- several types of architectures possible

[image]

How to manage state of application?

[image]
- understand dependencies btw tasks
- managing states
  + aws step functions > call out diff compute
  + build workflows

[image x2]

How does serverless polling

- synch calls > no lambda functions

## Operational model of serveless/microservices

There are some op responsibilities:
- aws vs serverless

[image]

### What is serverless on operational model

- high available/secure
- no provision

[image]

Categories of services

- compute
- datastore
- integration

[image]

### Comparison of ops responsibilities

what aws does vs what customer manages

### Distributed tracing and segmenting and sub-segmenting

- way to tye the diff services together
- path of a system of 3rd party provider (sub segment)

[image]

Example:
aws x-ray service

[image]

### Troubleshooting sql queries

 - why one query taking more time
 - add metadata to trace
- sql performance logs
impact: from asynch to sync calls
- by user of service > impact: SLAs
- business analytics

[image x2]

## Changes to the delivery of Software

- deploys on diff pipelines

How to deploy on serverless?

- in a Monolith

[image]

- Microservice development lifecycle
+ decouple pipeline and delivery

[image]

### Some best practices

[image]

### AWS for CI/CD

[image]

### ...
[image]

### AWS cloud development kit

- use of constructs
[image]


## Further learning
[image]

- developing on AWS
- certified dev associate
- certified devops engineer

# Chat about microservices
[image]

## Distributed tracing
- opentelemetry
https://github.com/open-telemetry

[image]

## Aws step functions

# Modern application dev > the art of the state machines
40 min

## Agenda

[image]

## Getting things done

in Monolith, everything deployed together in one service

in microservice, we split into models
- agility increase
  + teams focus on their service only
  + one datastore for the team
- scalability
  + each service can scale alone
  + horizontal scaling (e.g. databases, services)

[image]

Distributed systems hard to cordinate and debug
- what was the problem
- how services communicate to each other (e.g. message bus)

[imagge]

## Chroeography

Example simple banking systems

[image]

How Chroeography works:
- emit events chain of events
- respond to chain of events
- events transmitted by event bus

[image]

## Orchestration - alternative to Chroeography

- one process manages the state and calls appropriate services in turn

IF ELSE statements

[image]

## When use Chroeography vs Orchestration

[image]

### Example Orchestration

[image]

- Decouple from workflow if can be done in paralel

[image]

- is intervention required by human

[image]

  + Takes advantage of parallelism
  + Concept of state machine corresponds to this.

### What are state machines

[image]

- explicitly codify intended exec of code

## AWS step functions

managed state machine service on the cloud
- high available
- scalability
  - built-in error handling
  - service integration
  - workflow automation  
  - easy audit of execution of code
[image]

### How does it works

[image x2]

+ pass vs wait states
+ paralel states > many state machines inside bigger one (parallelism)
+ choice states

[image]

+ state transitions

### Amazon states language

- express with json

[image]

### Example

- perform a task

[image]

- Exec branches in paralel

[image]

- Making a choice

[image]

- Waiting for a callback (instead of forcing call)

[image x2]

## Step function dive deeper

State types:

- task
- choice
- Wait
- paralel
- map
- succeed
- fail
- pass

[image]

AWS service integrations

[image]

Working with step functinos

[image]

+ monitoring of executions > nice one!

### Errror handling

[image]

### Development Tips

https://docs.aws.amazon.com/step-functions/latest/dg/sfn-local.html
https://github.com/awslabs/statelint
https://github.com/horike37/serverless-step-functions
https://marketplace.visualstudio.com/items?itemName=paulshestakov.aws-step-functions-constructor

[image]

### Examples

[image]

Coca-cola: https://www.youtube.com/watch?v=sMaqd5J69Ns

### Key benefits of step functions

[image]

### Further learning

[image]

https://aws.amazon.com/getting-started/tutorials/create-a-serverless-workflow-step-functions-lambda/
https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html
https://aws.amazon.com/step-functions/resources/#Reference_architectures

Exams and further training
[image]

### Chat

[image]

# Event driven

## Event-driven architectures

- losely coupled
- managed

## Microses vs Monolith

- more complex
- scale more easily

end goal

[image]

## Event bus

AWS event bridge

[image x2]

### Amazon EventBridge

[nomenclature image]

Basics:
[image x4]

Event structure:
[event and rules image]

### What does it mean?

- write less code
- reduce ops overhead
- connect data from other apps

[image]

### Common use cases

[image]

- take actions
- run workflows
- **apply intelligence**
- audit and analyse
- sync data

[image]

## Dive deeper into Event-bridge

CLI
1. Create event bus
[image]

2. Create rules > subset of event
[image]

3. Associate target to rule > e.g. lambda function
[image]

4. Publish events ie put event into bus
[image x2]

5. Security > e.g. give permission to invoke lambda function
[image]

### Key limits to AWS Event-Bridges

[image]

### Examples (console)

[image x4]

Datadog
[image]

Pagerduty
[image]

## Further Learning with event-bridge

[image]

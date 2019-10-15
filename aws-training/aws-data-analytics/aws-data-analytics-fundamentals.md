# Data Analytics fundamentals

https://www.aws.training/Details/eLearning?id=35364

Prerequisites

- Working knowledge of database concepts
- Basic understanding of data storage, processing, and analytics
- Experience with enterprise IT systems

Duration
3.5 hours

Description
In this self-paced course, you learn about the process for planning data analysis solutions and the various data analytic processes that are involved. This course takes you through five key factors that indicate the need for specific AWS services in collecting, processing, analyzing, and presenting your data. This includes learning basic architectures, value propositions, and potential use cases. The course introduces you to the AWS services and solutions to help you build and enhance data analysis solutions.

Audience:
Data architects
Data scientists
Data analysts

## Lesson 1: Introduction to data analysis solutions

Goals:
- Data analytics and data analysis solutions
- Introduction to the challenges of data analytics

In this lesson, we introduce the concept of data analytics and data analysis solutions and discuss the **challenges of working with large data sets** that must rapidly produce meaningful insights. We also introduce you to the five challenges (the 5 Vs) of data analysis. Lastly, we define what you need to know plan your data analysis solution.

What is data analysis about:
- storage
- process
- analyse
- present

## Definitions:
**Data analysis** is the process of compiling, processing, and analyzing data so that you can use it to make decisions.

**Analytics** is the systematic analysis of data. **Data analytics** is the specific analytical process being applied.

Effective data analysis solutions require both **storage** and the ability to analyze data in **near real time, with low latency**, while yielding high-value returns.

[image]

## Topic 1: Data analytics and data analysis solutions

### Challenges
- storage without use of data
- five key challenges: **volume, velocity, variety, veracity, and value.**

### Types of data

- Human generated data: data created directly by humans typing information into a system or application
- Computer generated data: data is created by applications without direct human instruction. It often results from human-generated input being combined with additional information gathered by a system.
- Computer generated logs: data is generated by logging the actions of applications and the behavior of systems and network devices within a network
  + semistructured log files
  + be stored in binary format
  + pattern matching and correlation

### Big data
+ massive datasets
+ fast speeds
+ rapid insights

* Not everyone doing all three

### Data analysis = manage data management cycle
- collect and storage
- processing and analysing
- visualising

Components of data analysis solutions

[image]

### Definitions:
The collect component is where the services assemble data from many sources.
The store component stores data in repositories.
The process component is where services manipulate data into needed forms.
The consume component is where data is presented in the required formats.

## Topic 2: Introduction to the challenges of data analytics

### Challenges:
five key challenges: **volume, velocity, variety, veracity, and value.**

- Volume: amount of data that a solution must handle. The solution must do it efficiently and be able to distribute the load across enough servers to handle the next V: velocity.

- Velocity: speed at which data enters and flows through your solution. **ingest and process**

- variety: Ingesting data of many different types from many different sources.
  + structured, semistructured, unstructured data types.

- veracity: refers to the trustworthiness of your data. ie **provenance** of your data.
  + provenance = chain of custody for that data. accurate and consistent data.

- value: the bottom line.

### Plan for a data analysis solution

- Know where data come from: > **lessons 2 and 4**
  + dbs & filestores, streaming, public datasets..
- Know options for processing data > **lessons 3 and 5**
  + collecting/ingesting
  + cleansing
  + transform
  + load into datastore

[image]

- Know what to do with the data > **lesson 6**
  + reports, dashboards

### Summary
- concept of data Analytics
- five Vs of challenges
- plan data analysis solution

next: how to tackle high volume data

## Lesson 2: Volume – data storage

Goals:
- Introduction to Amazon Simple Storage Service (**Amazon S3**)
- Introduction to **data lakes**
- Introduction to **data storage methods**

In this lesson, we will discuss the challenges posed by a **high volume of data**. We will also discuss the scope of data source types you may need to ingest and store. We will end with a discussion of the AWS options available for storing data.

### Volume challenge
- devices collect data
- send data to server for processing
e.g. 4M videos/min
e.g. all data = 175 zettabytes/year in 2025

**Challenges**
- large amounts of datastorage
- many data sources
- scalable solutions = volume and traffic

### Types of data for analysis
- structured/relational data > 10%
  + stored in relational
  + rules and constraints
- semi structure data > 10%
  + nosql database
  + not strict structure
  + key-value pairs
  + xml or json files
  + temporary in nature
e.g. browser cache, social apps
- unstructured data > **80%**
  + not structured in a consistent way
  + files or objects
  + "untouchable" > requires tagging and cataloging
e.g. images, email, text files, videos

[image]

## Topic 1:Introduction to Amazon S3

https://aws.amazon.com/s3/?nc2=h_m1

Data analysis solutions can ingest data from just about anywhere. However, the **closer your data is to your processing system**, the better that processing system will perform. In AWS, the Amazon Simple Storage Service (Amazon S3) is the best place to **store all of your semistructured and unstructured data**.

### Amazon S3
- backbone of storage solution
- store day temporarily

Characteristics of S3
- web service: object store ie files
- store anything
- scalable
- durable
- security
- performance
- native online (http)

How it works
- Buckets: like file folders
- Move data into buckets: can be size

Key features:
+ Can decouple storage and processing
  + store all data types in their native formats
  + Launch Amazon Elastic Compute Cloud (Amazon EC2)
  + Optimise EC2: CPU, memory, and bandwidth
+ Parallelisation: access any storage from any process (with no impact)
+ Central location for analytical processes > avoid move from store to process system  
+ Integration with clusterless/serverless AWS
  + Lambda: run code without provisioning or managing servers
  + Athena: query Amazon S3 directly
+ Stand APIs

### Concepts:
Amazon S3 stores data as objects within buckets.
**object**:
An object is composed of a file and any metadata that describes that file. To store an object in Amazon S3, you upload the file you want to store into a bucket. When you upload a file, you can set permissions on the object and add any metadata.

**bucket**:
Buckets are logical containers for objects. You can have one or more buckets in your account and can control access for each bucket individually. You control who can create, delete, and list objects in the bucket. You can also view access logs for the bucket and its objects and choose the geographical region where Amazon S3 will store the bucket and its contents.

[image]


### Access to objects
Once objects have been stored in an Amazon S3 bucket, they are given an **object key**. Use this, along with the bucket name, to access the object.

Below is an example of a URL for a single object in a bucket named doc, with an object key composed of the prefix 2006-03-01 and the file named AmazonS3.html.

[image]

An **object key is the unique identifier for an object in a bucket**. Because the combination of a bucket, key, and version ID uniquely identifies each object, you can think of Amazon S3 as a basic **data map between "bucket + key + version" and the object itself**. Every object in Amazon S3 can be uniquely addressed through the combination of the web service endpoint, bucket name, key, and (optionally) version.

object metadata: https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingMetadata.html#object-metadata

## Topic 2: Introduction to data lakes

- How Amazon S3 organizes data

Data lake: architectural concept that helps you manage multiple data types from multiple sources, both structured and unstructured, through a single set of tools.

[image]

### What does a data lake do:
- Takes S3 buckets
- Organise data inside Buckets
- Structured and unstructured
- Unified set of tools offered by AWS
  + manage the entire data lake without treating each bucket as separate

### Features:
- break data silos
- single consistent source of truth (raw format storage)
- no need to transform data to make useful

Single source of truth:
- dataset that can be used for all processing and Analytics

### Benefits of data lakes
- single source of truth
- store any data type, no structure required
- used in AI and ML

### Data lake on AWS:
- cost effective Storage
- security and compliance
- Data collection and ingestion tools e.g. AWS Kinesis (streaming), AWS Snowball (on prem)
- Categorise/manage data e.g. AWS Glue (prepare, load from datalake, catalogs, searchable)
- Obtain insights e.g. Spark, Hadoop

### AWS EMR and data lakes
- Apache Hadoop and Spark are both supported
- data processing solutions on S3

Further reading:
https://aws.amazon.com/big-data/datalakes-and-analytics/

Next: nature of data storage within data processing applications.

## Topic 3: Introduction to data storage methods
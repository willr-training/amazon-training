Modernise analytics and data infrastructure
# Session 1:Modernize and monetize your data platform
Craig Stires
15 mins

## types of organisations

[image]

## How to start

[image]
[image]

## Automating heavy lifting

fully managed services
- diff services
[image]

## Workflow of how to build
[image] monetise core business

e.g.
[image]

from transactions to spending tracking services
- transform event pipeline into data pipeline
[image] Spark EMR example

2. model creation

e.g.
[image x2]
Hadoop: capture data on cluster
Sandbox: low maintenance

3. monetise influence
- real time engagement with customers
[image]

e.g.: important culture of experimentation
ex: use of speech Recognition in banking app
[image]

4. Bigger ambition: monetise ecosystem
[image]

- package to monetise marketplace with 3rd parties.
- aggregate enriched data
- federated apis

e.g.: Open banking regulations
3rd party api to request data

5. Decentralised analytics - value scaling
[image]

[iamge]
- distribute model of analytics and ML

## Summary

- Broadest/feature rich platform
- Governance/security + audit + compliance
- Cost optimisation to lower prices e.g. elastic compute + large storage S3

## Further reading

[image]

# Session 2: Relational databases on AWS - Amazon EC2, Amazon RDS, or Amazon Aurora?
35 mins
Blair Layton

- Amazon RDS
- Amazon Aurora

## Agenda
[image]

## RDS

### Why AWS
EC2 vs managed databases services?

- value add of DBAs

[image] - on premises
vs
[image] EC2

### If choose RDS then

[image]

### RDS databases supported

[images]

### DB security and compliance

- secure a network config
- several ways to do it

[image] - managed connectivity

- Database IP firewall protection itself

[]

- Governed access by user and Role

+ use of IAM
[image]

- In transit encryption - SSL

[image]

- At rest encryptio
storage system at-rest encryption

[iamge]

### RDS compliance matrix

[image]

### Sizing db server

- Servers as instances
+ servers are now **instances**

[image]

- Instance types

new Intel based EC2 z1d
[image]

- Storage
+ start with general purpose
+ easier to provision
[image]

- Choice of instances
[iamge]

- Comparison summary - sizing
[iamge]

+ Aurora

### Scaling db servers

[image]

- Scaling reads with read replicas
+ intra regions

- Oracle and SQL - options

[image]

## Demo - scaling aurora cluster

[sample image]

### Backup and recovery

- Automatic

Requirements:
- automatic backups to S3(too)
- 5min
[iamge]

- On user snapshots

[iamge]

- Snapshots

+ Use cases
[iamge]

### HA and disaster recovery

- minimal deployment
[iamge] - single AZ environment

- high availabilty - multi AZ

+ sync replication
[image]

### Upgrades and patching

- Upgrades:
+ full upgrade from one version to another
+ user initiated or auto

[iamge]

- Patching
[image]
+ Aurora offers private patches - enterprise supported

### Retiring DB servers

- Delete protection turned off
+ process to prevent deletion
[iamge]

### Metrics and monitoring

- Standard vs enhanced monitoring
+ outside
[image x2]

- Accessing performance insights
+ inside
+ CPU bottleneck

[image]

- Native and 3rd party tools

[image]

### Migrating databases

- Goal: database freedom
+ schema conversation tool e.g. oracle to Aurora
+ database migration saervice
[image]

- AWS DMS sources and targets
[image]


### Cost management

[iamge]
+ stop/start
+ scale up/down
+ right Storage
+ right edition
+ RIs - reserve instance

### Comparison of RDS and aurora
[image]

+ lots of innovation on Aurora

### Learn more
[image]

aws.traning

# Session 3: Building next-generation data lakes, data warehouse, and analytics on AWS
40 mins
Aneesh Chandra PN

## Agenda
[iamge]

## Key characteristics of data platform
[image]

+ consume
+ manage
+ govern/secure
+ collect and collect

## Components of a data lakes
[iamge]

+ data sources
> raw and processed
> data warehouse
> data consumptions

## The core datalake
- Storage and cataloguing

[iamge]

Amazon S3: obj Storage
- ticks all boxes

Amazon s3 glacier: for archive and backups

AWS glue data cataloguing
- auto discover data on S3

## Data ingestion
[iamge]

- Batch data ingestion- AWS Glue + ETL tools + SFTP put
[image]

- Realtime data ingestion
[iamge]
+ kiinesis data streams
> kinesis analytics or
> EMR etc

- Amazon managed stream for Kafka - MSK
[image]
+ zookeeper under the hood

## Data processing

- Amazon EMR
+ managed hadiopp
+ Spark
[iamge]

- AWS Glue
+ run spark code in serverless manner
[image]

## Consumption of data and insights

Use case: BI and reporting
- Amazon Redshift
[image]

- Redshift spectrum
[image]
+ extend redshoft tp S3

- Redshift out of the box
[image]
+ concurrency scaling
+ auto analise

- Amazon athena
+ query s3 directly
+ pay per data scanned
+ workgroup thresholds

- Amazon QuickSight
[image]

+ no server to manage

- Amazon sageMaker
+ train and deploy
+ parameter optimisation of models
[image]

## Amazon lake formation
+ monitor and audit data lake

- Load data
[image]

- Discoverability and Governance
[image]
+ at data catalog level
[image]

## Reference architecture - summary

- Data lake on AWS
[image]

- Demo
[image] - data architecture

+ storage
+ data locations
++ grant permissions IAM and admin
+ data importers > creates crawler and jobs
++ add data importers
++ create db
++ grant permission: admin and IAM (service Role)
++ import target
+ crawler
+ jobs created > connect to source and push into S3
+ data catalog > databases> tables
+ S3 console > parquet files (target defined)
+ assign permissions > BI user / SME user
++ permission flow down to other services
e.g. Athena

## Further learning

[image required]

# Session 4:Building real-time stream processing pipelines on AWS
30 mins
Gabe Hollombe

## Agenda
[iamge]

## Why stream is valuable
[image]
+ time to action close when generated
+ data to decision making
+ e.g. fraud Detection

## What streaming data
[iamhe]
+ ingestion
+ processd
+ analytics

- use cases of streaming
[image]

## Challenges of streaming data
[image]

## Solutions to streaming data
[image]
- Kinesis data streams
- Kinesis data analuytcs
- Kinesis firehose
- Stream for kafka MSK

## Stream data sources
[image]

+ mob app actions
+ app logs
+ IoT sensors - data into cloud

## Get data into stream - ingestion
[image]
+ toolkits/lib Solutions
+ service integration solutions
+ 3rd party with plugins/extensions

## Where store data - stream destinations

- Kinesis data streams
[image]

- Kinesis data firehose
[image]
+ elastic
+ no management
+ near realtime (less than kinesis stream)

- Kinesis streams vs kinesis firehose
[image]

- Amazon MSK: Kafka on aws - new service
[iamge]
v1.1.1
[image]

- Comparison MSK vs Kinesis data streams
[image]

## Processing data
[image]

- Options for strean Processing
[image]
+ Kinesis
+ services - Lambda or EMR
+ 3rd party

- Kinesis data analytics
[image]

+ process of how-to
[image]
+ SQL for simple and fast
[image]

+ more advanced - JAVA + apache flink
[image]

## Data destination for consumption
[image x1]

- Options
[image]
+ S3
+ Athena - adhoc
+ Redshift

## Example of architecture
[image]

## Demo
- aws solutions
+ managed by architects
[image] - kinesis analytics solution
[image of flow]

+ auto deployment
++ auto testing
+ cloud watch dashboard

## Common architecture patterns

Stream > store > process> amazon AI > store/dashboard
[image x3]

Example
[image]

## Best practices

[image]
+ different tools for diff phases of data pipelines
+ right tool
+ leveraged aws managed services
+ cost conscious => big data <> big cost

## Learn further
[image]
aws.training


# Session 5:Machine Learning with Amazon SageMaker
30 mins
Spencer Marley

## Session Goal:
Create notebook using sageMaker examples

## Whats ML
[image]

- Goals of types of learning
[iamge]

## AWS to help with ML

[image] - Stack
+ AI services
+ ML services : customise ML models e.g. sageMaker
+ ML Frameworks + infrastructure: need to config of infrastructure

- c5n

## Amazon SageMaker
[image]
+ pre-built notebooks
+ high performance
+ one click training : location and stance types
+ optimisation: hyperparamter
+ one click deploy
+ managed auto scaling + maintenance

## Amazon sageMaker Groundtruth
[image]

## DL Frameworks

- TensorFlow
[image]

- Apache MXNET
[image]

## Demo (sagemaker)

+ create notebook instance
++ create IAM Role
++ options

+ jupyter
++ examples
++ use>create copy
++ sagemaker examples
+ stop notebook instances

## Reinforcement learning

 - Terms in RL
 [image]

 - ex: AWS DeepRacer

## Demo AWS DeepRacer
Limited regions

## More resources

+ free tier
[image]
+ ML university
[image]

+ other courses
[image]

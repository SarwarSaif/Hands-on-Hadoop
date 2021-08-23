# Hands-on-Hadoop

## What is Hadoop?
"An open source software platform for distributed storage and distributed processing of very large data sets on computer clusters built from commodity hardware" - Hortonworks

## Hadoop History 
- Google published GFS and MapReduce papers in 2003-2004. GFS inspired Hadoop's distributed storgae system and MapReduce inspired Hadoop's distributed processing
- Yahoo! was building "Nutch", an open source web search engine at the same time.
- Hadoop was primarily driven by Doug Cutting and Tom White in 2006. 
- Hadoop was named after a stuffed elephant toy of Doug cutting's kid.
- It's been evolving ever since and build a large ecosystem around it. 

## Why Hadoop?
- Now-a-days data is too big to handle through one computer as companies generate terrabytes of data per day.
- Databases like Oracle uses Vertical scaling which doesn't cut it. They have problems like:
  - Disk seek times
  - Hardware failures
  - Processing times 
- Hadoop uses Horizontal scaling which is linear. Hadoop uses clustures of computers with many many of many hard drives where they can all be seeking in parellel with all their independent disk heads. Don't have a single Point of Failure. Hadoop also offers parallel processing throughout the clusters that can take advantage of all the CPUs. 
- Hadoop is not just for batch processing anymore.

<a href="https://www.section.io/blog/scaling-horizontally-vs-vertically/">Scaling Horizontally vs. Scaling Vertically</a>
"Horizontal scaling means scaling by adding more machines to your pool of resources (also described as “scaling out”), whereas vertical scaling refers to scaling by adding more power (e.g. CPU, RAM) to an existing machine (also described as “scaling up”)."

## Hadoop Ecosystem Overview
### Core Hadoop Ecosystem
- HDFS (Hadoop Distributed File System) 
  - It let us distribute the storages of big data into clusters of computers. 
  - Maintains Redundant copy of the data.
- YARN 
  - Manages the resources in the clusters.
  - Decides when and what node to run next, which nodes are available and which nodes are not.
- MapReduce
  - It's a program model that helps to process a dataset across clusters.
  - MapReduce has two scripts: 1. MapReduce and 2. Reducer
    - It can parallel an entire dataset across different clusters.
    - Reducers aggregate all processed data together.
- Pig 
  - A High Level Programming API that let us write SQL like Scripting language.
  - It sits on top of MapReduce.
- Hive
  - It also sit on top of MapReduce and also have similar similar functionalities as PIG.
  - It's works like a SQL Database where you can query using SQL directly. 
  - I can be connected through shell client or ODBC.
- Apache Ambari
  - It sits on top of everything and let us visulize and monetize all other services beneath it.
  - Such as: What's running on the cluster, what systems are using how many resources.
  - It also has Views which let use execute hive or pig querys to get results and connect databases and so on.
- MESOS
  - An alternative to YARN.
  - It's a Resource Negotiator like YARN.
- Spark
  - It's sitting on the same level of MapReduce.
  - It can do query same as MapReduce by utilizing YARN and MESOS.
  - It also needs Spark scripting using languages like python, java, scala.
  - It's extremely fast and powerful.
  - It's also really efficient and reliable for processing data.
  - It can handle SQL query, do machine learning across clusters of data, handle streaming data in real-time. It's extremely versatile and under active development.
- TEZ
  - Usually used in conjunction with Hive to accelerate it.
- Apache HBASE
  - It's a NoSQL Database. A columner storage.
  - Really really fast Database meant for very large transaction rates.
  - It can exposed the data stored on the cluster with a very fast speed.
- Apache Storm 
  - A way of processing streaming data such as sensor data, log data and so on.
  - Spark solves the same problem but Storm does it in a different way.
  - Data doesn't need to be in batches and can be fed into machine learning models and transformation procedures.
- OOZIE
  - It's a way of scheduling job in the cluster.
  - Task that needs to happen on the hadoop cluster that involves many different steps and may be many different systems, the scheduling can be reliably and efficiently handled by OOZIE.
- Zookeeper
  - To keep track of which nodes are up or which are down.
  - It's a very realiable way to keep track of the shared states across the clusters.
- Sqoop (For Data Ingestion onto HDFS from external sources)
  -  It's a way for tying hadoop database with a relational/legacy databases.
  -  Anything that can talk to ODBC or JDBC can be transformed by Sqoop into HDFS file system.
- Flume (For Data Ingestion onto HDFS from external sources)
  - It's a way of actually transporting web logs at a very large scale very reliably to the cluster at real time.
- Kafka (For Data Ingestion onto HDFS from external sources)
  - It also solves a similar problem like flume.
  - It can basically collect data of any sort from a cluster of PCs from a cluster of web servers or whatever and broadcast that into a hadoop cluster.

### External Data Storage
- MySQL
- MongoDB
- Cassandra

### Query Engines
- Apache Drill
  - It allows to write SQL queries that will work across a wide range of NoSQL databases.
- HUE
  - It's kind of similar to Ambari 
- Apache Phoenix
  - Similar to apache drill and let us do SQL style queries across entire range.
  - But it also give us ACID gurantees and OLTP.
- Presto 
  - Another way to execute queries across entire cluster. 
- Apache Zeppelin
  - It takes more of a notebook type approach to the UI and how we interact with the cluster.
  
  
## HDFS (Haddop DIstributed File System)
### What is HDFS?
  - It's made for handling large files. It is basically optimized for very large files which can be distributed and broken up across and entire cluster.
  - Breaks the files into blocks and each blocks are 128 MB by default. 
  - Different blocks can be stored across several commodity computers. If a computer goes down HDFS can delat with that by retrieving information from a different computer where it stored the backups.

### HDFS Architecture
There are two types of Nodes.
1. Name Node 
  - It's a single node.
  - It keeps track of where all different blocks live. 
  - It also maintains an edit log which maintains a record of whats's being modified or what's being stored on the data nodes to keep track of everything.
  - 
3. Data Nodes
  - There can be multiple data nodes.
  - These nodes are what actually store each block of each file. 
  - These nodes can talk to each other as well to maintain those copies and replication of those blocks.

#### Reading a File in HDFS
- Suppose an application running on a dclient node which needs access to data stored on the HDFS. First thing that it will do that it'll talk to the Name node for the the desired files. Name node will search the files and return the blocks locations for each file.
- 


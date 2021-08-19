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
  - A High Level Scripting language sits on top of MapReduce
- 

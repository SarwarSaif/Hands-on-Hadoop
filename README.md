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
- Horizontal scaling is linear. Hadoop uses clustures of computers with many many of many hard drives where they can all be seeking in parellel with all their independent disk heads. Don't have a single Point of Failure
- Hadoop is not just for batch processing anymore

<a href="https://www.section.io/blog/scaling-horizontally-vs-vertically/">Scaling Horizontally vs. Scaling Vertically</a>
"Horizontal scaling means scaling by adding more machines to your pool of resources (also described as “scaling out”), whereas vertical scaling refers to scaling by adding more power (e.g. CPU, RAM) to an existing machine (also described as “scaling up”)."


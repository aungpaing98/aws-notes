Store and Process vast amount of data efficiently using cluster of computation hardware.

## Components

### 1. Storage Unit
[HDFS](HDFS.md) : Hadoop Distributed File system
It use Replication method, each splitted data is replicated in many blocks, to prevent the data loss.

### 2. Process
MapReduce

### 3. YARN : Yet Another resource manager
It consists of four main parties
- Resource manager
- Node manager
- Application master
- Container
Application master and container request resource to Resource manager via Node manager.

In additional, hadoop ecosystem consists of other components like Hive, Pig, Apache Spark
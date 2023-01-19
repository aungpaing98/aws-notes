- Elastic MapReduce
- Managed [[Hadoop]] framework on EC2 instances
- Includes Spark, HBase, [[Presto]], [[Flink]], Hive & more
- EMR notebooks
- Several integration points with AWS
- Prepare big data for pre-processing for Machine learning

### EMR Cluster
- Master node
	- Manage the cluster 
- Core node
	- Hosts [[HDFS]] data and run tasks
- Task node
	- Run tasks, does not host data

Note:
	Each node is a separate EC2 instance.
	If a single machine can handle all processing, a master node is enough for the cluster.
	If multiple nodes are required in the cluster, there must be at least one core node. Taks node does not store any data and just focus on computing.

### EMR Usage
- Transient (automative terminate) vs Long-Running (manual terminate) Clusters
	- Can spin up task nodes using spot instance for temporary capacity
	- Can use reserved instances on long-running clusters to save money.
- Connect directly to master to run jobs
- EMR [[Serverless]] lets AWS scale your nodes automatically.

### Storage
- [[HDFS]]
- EMRFS : access S3 as if it were [[HDFS]]
- Local file system
- EBS for [[HDFS]]

### AWS Integration
- EC2 for the instances that comprise the nodes
- VPC to configure the virtual network
- S3 to store input and output data
- CloudWatch to monitor cluster performance and configure alarms
- IAM to configure permissions
- CloudTrail to audit requests made to the service
- Data Pipeline to schedule and start the cluster.

### Promises
- Charges by hour
	- Plus EC2 charges
- Provisions new nodes if a core node fails
- Can add and remove tasks nodes on the fly
- Can resize a running cluster's core nodes

### Security
- [[IAM]] policies
- Kerberos
- SSH
- [[IAM]] roles

### Choosing Instance Types
- Master node:
	- m4.large if < 50 nodes, m4.xlarge if > 50 nodes
- Core & task nodes:
	- m4.large is usually good
	- If cluster waits a lot on external dependencies (eg. web crawler), t2.medium
	- Computation-intensive : high CPU instances
	- Database, memory-caching : high memory instances
	- Network / CPU-intensive (NLP, ML) - cluster computer instances
- Spot instances
	- Good choice for task nodes
	- Only use on core & master if testing or very cost-sensitive : Risk partial data loss.
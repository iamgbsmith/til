# What Is OpenSearch

__Category: AWS__

AWS OpenSearch is an open-source fully managed Elasticsearch service instance. OpenSearch is compatible with Elasticsearch APIs and integrates with CloudWatch. Data can be ingested from Kinesis Data Firehose, S3, CloudWatch Logs, and DynamoDB using Lambda.

When you launch an OpenSearch instance you need to create a search domain (cluster) which has:

* Master Modes that manage the cluster and monitor health of nodes in the cluster. 
* Data Nodes (also known as worker nodes) which are responsible for storing data and performing searches on the data which is stored in shards.

You can scale the cluster using an API call or using the AWS console. 

Clusters can store up to 3PB of data and be replicated to a different AZ for high availability and allows use of cost-effective UltraWarm and cold storage for read-only data.

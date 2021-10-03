# S3 Storage Classes

__Category: AWS__

S3 provides different storage classes to suit your architectural requirements. You should choose a storage class based on whether you need to store data (objects) for a short or long term duration and whether you require immediate access to data. 

Prices typically reduce as you move from short term to long term storage although this requires trading off time to restore/retrieve data.

| Name               | Class           | Retrieval Time | Types of Use |
| ------------------ |-----------------|--------------|----------------|
| S3 Standard            | General Purpose | Immediate | Designed for a frequently accessed data such as, cloud applications, dynamic websites, content distribution, mobile and gaming applications, and big data analytics. The de-facto S3 Standard offers high durability, availability, and performance object storage for frequently accessed data. |
| S3 Intelligent Tiering | Unknown or Changing Access | Variable |Designed for data with unknown, changing, or unpredictable access patterns, independent of object size or retention period. Use S3 Intelligent-Tiering as the default storage class for data lakes, analytics, and new applications. Objects are moved between tiers based on when they were last accessed. |
| S3 Standard-Infrequent Access (S3 Standard-IA) | Infrequent Access | Immediate | Used for data that is accessed less frequently, but requires rapid access when needed. Use for long-term storage, backups, and as a data store for disaster recovery files. |
| S3 One Zone-Infrequent Access (S3 One Zone-IA) | Infrequent Access | Immediate | Ideal for customers who want a lower-cost option for infrequently accessed data but do not require the availability and resilience of S3 Standard or S3 Standard-IA. Stores data in a single AZ and costs 20% less than S3 Standard-IA. Use for storing secondary backup copies of on-premises data or easily re-creatable data. |
| S3 Glacier | Archive | Minutes to Hours | Ideal for low-cost storage amd for data archival at costs that are competitive with or cheaper than on-premise solutions. Provides three retrieval options that range from a few minutes to hours. |
| S3 Glacier Deep Archive | Archive | Within 12 hours | Designed for customers in highly-regulated industries, such as the financial services, healthcare, and public sectors that retain data sets for 7-10 years or longer to meet regulatory compliance requirements. It is the lowest-cost storage class and supports long-term retention and digital preservation for data that may be accessed once or twice in a year. Data can be restored within 12 hours. |

__Note:__  S3 Storage Classes can be configured at the object level and a single bucket can contain objects stored across S3 Standard, S3 Intelligent-Tiering, S3 Standard-IA, and S3 One Zone-IA. You can use S3 Lifecycle policies to automatically transition objects between storage classes without requiring any application changes.

See [Amazon S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/) for more details.

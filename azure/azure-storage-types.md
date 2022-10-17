# Azure Storage Types

__Category: Azure__

Azure provides four storage types which can be securely accessed over HTTPS.

| Name                | Function           | 
| ------------------- |--------------------| 
| Azure Blob Storage  | General purpose storage for objects such as video, audio, or text files. Provides sixteen nine of durability with geo-replication and encryption at rest. Blobs are addressed using the URL format `https://<storage account>.blob.core.windows.net/<container>/<blob>` | 
| Azure Files         | Provides distributed, cloud file-share capabilities and can be accessed using SMB and NFS prototcols. Can be mounted concurrently by cloud or on-premise deployments of Windows, Linux and macOS. Files are addressed using the URL format `https://<storage account>.file.core.windows.net/<container>/<file>` |
| Azure Queue Storage | Used to store queue messages up to 64KB in size. The maximum time-to-live can be any postiive number. Queues are addressed using the URL format `https://<storage account>.queue.core.windows.net/<queue>` |
| Azure Cosmos DB for Table | A replacement for Azure Table Storage. Stores non-relational structured data using a key/value schemaless design. Data is distributed using geo-replication. |
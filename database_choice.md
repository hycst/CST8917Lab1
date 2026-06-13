##### CST 8917 Lab1 Database Choice

#####  Choice  Azure Cosmos DB

#####  Justification

For the Lab1 project, I would like select Azure Cosmos DB, because it stores JSON documents natively without requiring a predefined schema. 
Since the TextAnalyzer function already produces JSON output, the analysis results can be stored directly with minimal code changes. 
Furthermore, The serverless pricing model only charges for database operations, making it cost-effective for student projects and workloads with low request volumes. 
Finally, Azure Cosmos DB can integrate well with Azure Functions through the official Python SDK and automatically scales based on demand.

#####  Other Database Considered

##### Azure Table Storage

Compare to Azure Cosmos DB, Azure Table Storage is inexpensive and simple to use, but it has limited querying capabilities and does not naturally support complex JSON documents. 
It is better suited for simple key-value data.

#####  Azure SQL Database

For Azure SQL Database, it provides powerful relational queries, and transactions. But it requires a predefined schema. 
It is more suitable for structured relational data rather than flexible JSON documents.

#####  Azure Blob Storage

Azure Blob Storage is designed for storing files rather than structured data. 
Although JSON files can be stored as blobs, querying and managing historical analysis results would be inefficient.

#####  Cost Considerations

Generally, Azure Cosmos DB Serverless charges only for the requests and storage that are actually used. 
This eliminates the need to provision throughput in advance, making it an economical option for student projects. 
Azure also provides a free tier that includes free storage and request units, further reducing development costs.

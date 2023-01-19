## Glue Data Catalog
- metadata repository for all your tables
	- Automated schema inference
	- Schemas are versioned
- Integrates with Athena or Redshift Spectrum (schema & data discovery)
- Glue Crawlers can help build the Glue Data Catalog

---
## Glue Crawlers
- Crawlers go through the data to infer schemas and partitions
- Datatype : Works JSON, Parquet, CSV, relational store
- Data Storage : S3, Amazon Redshift, AWS RDS
- Run on Schedule or on demand
- Need IAM role / credentials to access the data stores.
- Will extract partitions based on how the S3 data is organized.
- Think up front about how querying (anthena) the data lake in S3.
- Query By date or By device?

---
## Glue ETL
- Generate ETL code in Python or Scala, code can be modified
- Can provide your own Spark or PySpark scripts
- Target can be S3, JDBC (RDS, Redshift), or in Glue Data Catalog
- Fully managed, cost effective, pay only for the resources consumed
- Jobs are run on a serverless [[Apache Spark|Spark]] platform
- Glue Scheduler to schedule the jobs
- Glue Triggers to automate job runs based on "events"

### Glue ETL - Transformation
#### Bundled Transformations
- DropField, DropNullFields : remove ( null ) fields
- Filter : specify a function to filter records
- Join : to enrich data
- Map : add fields, delete fields, perform external lookups
#### Machine Learning Transformations
- FindMatches ML : Identify duplicate or matching records in your dataset
#### [[Apache Spark]] transformations
- K-Means

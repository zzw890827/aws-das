# AWS DAS 01

1. A financial services company needs to aggregate daily stock trade data from the exchanges into a data store. The company requires that data be streamed directly into the data store, but also occasionally allows data to be modified using SQL. The solution should integrate complex, analytic queries running with minimal latency. The solution must provide a business intelligence dashboard that enables viewing of the top contributors to anomalies in stock prices. Which solution meets the company's requirements?
   - [ ] A. Use Amazon Kinesis Data Firehose to stream data to Amazon S3. Use Amazon Athena as a data source for Amazon QuickSight to create a business intelligence dashboard.
   - [ ] B. Use Amazon Kinesis Data Streams to stream data to Amazon Redshift. Use Amazon Redshift as a data source for Amazon QuickSight to create a business intelligence dashboard.
   - [ ] C. Use Amazon Kinesis Data Firehose to stream data to Amazon Redshift. Use Amazon Redshift as a data source for Amazon QuickSight to create a business intelligence dashboard.
   - [ ] D. Use Amazon Kinesis Data Streams to stream data to Amazon S3. Use Amazon Athena as a data source for Amazon QuickSight to create a business intelligence dashboard.
   <details>
      <summary>Answer</summary>

      C.

   </details>

2. A financial company hosts a data lake in Amazon S3 and a data warehouse on an Amazon Redshift cluster. The company uses Amazon QuickSight to build dashboards and wants to secure access from its on-premises Active Directory to Amazon QuickSight. How should the data be secured?
   - [ ] A. Use an Active Directory connector and single sign-on (SSO) in a corporate network environment.
   - [ ] B. Use a VPC endpoint to connect to Amazon S3 from Amazon QuickSight and an IAM role to authenticate Amazon Redshift.
   - [ ] C. Establish a secure connection by creating an S3 endpoint to connect Amazon QuickSight and a VPC endpoint to connect to Amazon Redshift.
   - [ ] D. Place Amazon QuickSight and Amazon Redshift in the security group and use an Amazon S3 endpoint to connect Amazon QuickSight to Amazon S3.

   <details>
      <summary>Answer</summary>

      A.

   </details>

3. A real estate company has a mission-critical application using Apache HBase in Amazon EMR. Amazon EMR is configured with a single master node. The company has over 5 TB of data stored on an Hadoop Distributed File System (HDFS). The company wants a cost-effective solution to make its HBase data highly available. Which architectural pattern meets company's requirements?
   - [ ] A. Use Spot Instances for core and task nodes and a Reserved Instance for the EMR master node. Configure the EMR cluster with multiple master nodes. Schedule automated snapshots using Amazon EventBridge.
   - [ ] B. Store the data on an EMR File System (EMRFS) instead of HDFS. Enable EMRFS consistent view. Create an EMR HBase cluster with multiple master nodes. Point the HBase root directory to an Amazon S3 bucket.
   - [ ] C. Store the data on an EMR File System (EMRFS) instead of HDFS and enable EMRFS consistent view. Run two separate EMR clusters in two different Availability Zones. Point both clusters to the same HBase root directory in the same Amazon S3 bucket.
   - [ ] D. Store the data on an EMR File System (EMRFS) instead of HDFS and enable EMRFS consistent view. Create a primary EMR HBase cluster with multiple master nodes. Create a secondary EMR HBase read-replica cluster in a separate Availability Zone. Point both clusters to the same HBase root directory in the same Amazon S3 bucket.

   <details>
      <summary>Answer</summary>

      C.

   </details>

4. A software company hosts an application on AWS, and new features are released weekly. As part of the application testing process, a solution must be developed that analyzes logs from each Amazon EC2 instance to ensure that the application is working as expected after each deployment. The collection and analysis solution should be highly available with the ability to display new information with minimal delays. Which method should the company use to collect and analyze the logs?
   - [ ] A. Enable detailed monitoring on Amazon EC2, use Amazon CloudWatch agent to store logs in Amazon S3, and use Amazon Athena for fast, interactive log analytics.
   - [ ] B. Use the Amazon Kinesis Producer Library (KPL) agent on Amazon EC2 to collect and send data to Kinesis Data Streams to further push the data to Amazon Elasticsearch Service and visualize using Amazon QuickSight.
   - [ ] C. Use the Amazon Kinesis Producer Library (KPL) agent on Amazon EC2 to collect and send data to Kinesis Data Firehose to further push the data to Amazon Elasticsearch Service and Kibana.
   - [ ] D. Use Amazon CloudWatch subscriptions to get access to a real-time feed of logs and have the logs delivered to Amazon Kinesis Data Streams to further push the data to Amazon Elasticsearch Service and Kibana.

   <details>
      <summary>Answer</summary>

      B.

   </details>

5. A data analyst is using AWS Glue to organize, cleanse, validate, and format a 200 GB dataset. The data analyst triggered the job to run with the Standard worker type. After 3 hours, the AWS Glue job status is still RUNNING. Logs from the job run show no error codes. The data analyst wants to improve the job execution time without overprovisioning. Which actions should the data analyst take?
   - [ ] A. Enable job bookmarks in AWS Glue to estimate the number of data processing units (DPUs). Based on the profiled metrics, increase the value of the executor- cores job parameter.
   - [ ] B. Enable job metrics in AWS Glue to estimate the number of data processing units (DPUs). Based on the profiled metrics, increase the value of the maximum capacity job parameter.
   - [ ] C. Enable job metrics in AWS Glue to estimate the number of data processing units (DPUs). Based on the profiled metrics, increase the value of the spark.yarn.executor.memoryOverhead job parameter.
   - [ ] D. Enable job bookmarks in AWS Glue to estimate the number of data processing units (DPUs). Based on the profiled metrics, increase the value of the num- executors job parameter.

   <details>
      <summary>Answer</summary>

      B.

   </details>

6. A company has a business unit uploading .csv files to an Amazon S3 bucket. The company's data platform team has set up an AWS Glue crawler to do discovery, and create tables and schemas. An AWS Glue job writes processed data from the created tables to an Amazon Redshift database. The AWS Glue job handles column mapping and creating the Amazon Redshift table appropriately. When the AWS Glue job is rerun for any reason in a day, duplicate records are introduced into the Amazon Redshift table. Which solution will update the Redshift table without duplicates when jobs are rerun?
   - [ ] A. Modify the AWS Glue job to copy the rows into a staging table. Add SQL commands to replace the existing rows in the main table as postactions in the DynamicFrameWriter class.
   - [ ] B. Load the previously inserted data into a MySQL database in the AWS Glue job. Perform an upsert operation in MySQL, and copy the results to the Amazon Redshift table.
   - [ ] C. Use Apache Spark's DataFrame dropDuplicates() API to eliminate duplicates and then write the data to Amazon Redshift.
   - [ ] D. Use the AWS Glue ResolveChoice built-in transform to select the most recent value of the column.

   <details>
      <summary>Answer</summary>

      A.

   </details>

7. A streaming application is reading data from Amazon Kinesis Data Streams and immediately writing the data to an Amazon S3 bucket every 10 seconds. The application is reading data from hundreds of shards. The batch interval cannot be changed due to a separate requirement. The data is being accessed by Amazon Athena. Users are seeing degradation in query performance as time progresses. Which action can help improve query performance?
   - [ ] A. Merge the files in Amazon S3 to form larger files.
   - [ ] B. Increase the number of shards in Kinesis Data Streams.
   - [ ] C. Add more memory and CPU capacity to the streaming application.
   - [ ] D. Write the files to multiple S3 buckets.

   <details>
      <summary>Answer</summary>

      A.

   </details>

8. A company uses Amazon OpenSearch Service (Amazon Elasticsearch Service) to store and analyze its website clickstream data. The company ingests 1 TB of data daily using Amazon Kinesis Data Firehose and stores one day's worth of data in an Amazon ES cluster. The company has very slow query performance on the Amazon ES index and occasionally sees errors from Kinesis Data Firehose when attempting to write to the index. The Amazon ES cluster has 10 nodes running a single index and 3 dedicated master nodes. Each data node has 1.5 TB of Amazon EBS storage attached and the cluster is configured with 1,000 shards. Occasionally, JVMMemoryPressure errors are found in the cluster logs. Which solution will improve the performance of Amazon ES?
   - [ ] A. Increase the memory of the Amazon ES master nodes.
   - [ ] B. Decrease the number of Amazon ES data nodes.
   - [ ] C. Decrease the number of Amazon ES shards for the index.
   - [ ] D. Increase the number of Amazon ES shards for the index.

   <details>
      <summary>Answer</summary>

      C.

   </details>

9. A manufacturing company has been collecting IoT sensor data from devices on its factory floor for a year and is storing the data in Amazon Redshift for daily analysis. A data analyst has determined that, at an expected ingestion rate of about 2 TB per day, the cluster will be undersized in less than 4 months. A long-term solution is needed. The data analyst has indicated that most queries only reference the most recent 13 months of data, yet there are also quarterly reports that need to query all the data generated from the past 7 years. The chief technology officer (CTO) is concerned about the costs, administrative effort, and performance of a long-term solution. Which solution should the data analyst use to meet these requirements?
   - [ ] A. Create a daily job in AWS Glue to UNLOAD records older than 13 months to Amazon S3 and delete those records from Amazon Redshift. Create an external table in Amazon Redshift to point to the S3 location. Use Amazon Redshift Spectrum to join to data that is older than 13 months.
   - [ ] B. Take a snapshot of the Amazon Redshift cluster. Restore the cluster to a new cluster using dense storage nodes with additional storage capacity.
   - [ ] C. Execute a CREATE TABLE AS SELECT (CTAS) statement to move records that are older than 13 months to quarterly partitioned data in Amazon Redshift Spectrum backed by Amazon S3.
   - [ ] D. Unload all the tables in Amazon Redshift to an Amazon S3 bucket using S3 Intelligent-Tiering. Use AWS Glue to crawl the S3 bucket location to create external tables in an AWS Glue Data Catalog. Create an Amazon EMR cluster using Auto Scaling for any daily analytics needs, and use Amazon Athena for the quarterly reports, with both using the same AWS Glue Data Catalog.

   <details>
      <summary>Answer</summary>

      A.

   </details>

10. An insurance company has raw data in JSON format that is sent without a predefined schedule through an Amazon Kinesis Data Firehose delivery stream to an Amazon S3 bucket. An AWS Glue crawler is scheduled to run every 8 hours to update the schema in the data catalog of the tables stored in the S3 bucket. Data analysts analyze the data using Apache Spark SQL on Amazon EMR set up with AWS Glue Data Catalog as the metastore. Data analysts say that, occasionally, the data they receive is stale. A data engineer needs to provide access to the most up-to-date data. Which solution meets these requirements?
    - [ ] A. Create an external schema based on the AWS Glue Data Catalog on the existing Amazon Redshift cluster to query new data in Amazon S3 with Amazon Redshift Spectrum.
    - [ ] B. Use Amazon CloudWatch Events with the rate (1 hour) expression to execute the AWS Glue crawler every hour.
    - [ ] C. Using the AWS CLI, modify the execution schedule of the AWS Glue crawler from 8 hours to 1 minute.
    - [ ] D. Run the AWS Glue crawler from an AWS Lambda function triggered by an S3:ObjectCreated:* event notification on the S3 bucket.

    <details>
      <summary>Answer</summary>

      D.

     </details>

11. A company that produces network devices has millions of users. Data is collected from the devices on an hourly basis and stored in an Amazon S3 data lake. The company runs analyses on the last 24 hours of data flow logs for abnormality detection and to troubleshoot and resolve user issues. The company also analyzes historical logs dating back 2 years to discover patterns and look for improvement opportunities. The data flow logs contain many metrics, such as date, timestamp, source IP, and target IP. There are about 10 billion events every day. How should this data be stored for optimal performance?
    - [ ] A. In Apache ORC partitioned by date and sorted by source IP
    - [ ] B. In compressed .csv partitioned by date and sorted by source IP
    - [ ] C. In Apache Parquet partitioned by source IP and sorted by date
    - [ ] D. In compressed nested JSON partitioned by source IP and sorted by date
    <details>
       <summary>Answer</summary>

       A.

    </details>

12. A banking company is currently using an Amazon Redshift cluster with dense storage (DS) nodes to store sensitive data. An audit found that the cluster is unencrypted. Compliance requirements state that a database with sensitive data must be encrypted through a hardware security module (HSM) with automated key rotation. Which combination of steps is required to achieve compliance? (Choose two.)
    - [ ] A. Set up a trusted connection with HSM using a client and server certificate with automatic key rotation.
    - [ ] B. Modify the cluster with an HSM encryption option and automatic key rotation.
    - [ ] C. Create a new HSM-encrypted Amazon Redshift cluster and migrate the data to the new cluster.
    - [ ] D. Enable HSM with key rotation through the AWS CLI.
    - [ ] E. Enable Elliptic Curve Diffie-Hellman Ephemeral (ECDHE) encryption in the HSM.

    <details>
       <summary>Answer</summary>

       AC.

    </details>

13. A company is planning to do a proof of concept for a machine learning (ML) project using Amazon SageMaker with a subset of existing on-premises data hosted in the company's 3 TB data warehouse. For part of the project, AWS Direct Connect is established and tested. To prepare the data for ML, data analysts are performing data curation. The data analysts want to perform multiple step, including mapping, dropping null fields, resolving choice, and splitting fields. The company needs the fastest solution to curate the data for this project. Which solution meets these requirements?
    - [ ] A. Ingest data into Amazon S3 using AWS DataSync and use Apache Spark scrips to curate the data in an Amazon EMR cluster. Store the curated data in Amazon S3 for ML processing.
    - [ ] B. Create custom ETL jobs on-premises to curate the data. Use AWS DMS to ingest data into Amazon S3 for ML processing.
    - [ ] C. Ingest data into Amazon S3 using AWS DMS. Use AWS Glue to perform data curation and store the data in Amazon S3 for ML processing.
    - [ ] D. Take a full backup of the data store and ship the backup files using AWS Snowball. Upload Snowball data into Amazon S3 and schedule data curation jobs using AWS Batch to prepare the data for ML.
    <details>
       <summary>Answer</summary>

       C.

    </details>

14. A US-based sneaker retail company launched its global website. All the transaction data is stored in Amazon RDS and curated historic transaction data is stored in Amazon Redshift in the us-east-1 Region. The business intelligence (BI) team wants to enhance the user experience by providing a dashboard for sneaker trends. The BI team decides to use Amazon QuickSight to render the website dashboards. During development, a team in Japan provisioned Amazon QuickSight in ap- northeast-1. The team is having difficulty connecting Amazon QuickSight from ap-northeast-1 to Amazon Redshift in us-east-1. Which solution will solve this issue and meet the requirements?
    - [ ] A. In the Amazon Redshift console, choose to configure cross-Region snapshots and set the destination Region as ap-northeast-1. Restore the Amazon Redshift Cluster from the snapshot and connect to Amazon QuickSight launched in ap-northeast-1.
    - [ ] B. Create a VPC endpoint from the Amazon QuickSight VPC to the Amazon Redshift VPC so Amazon QuickSight can access data from Amazon Redshift.
    - [ ] C. Create an Amazon Redshift endpoint connection string with Region information in the string and use this connection string in Amazon QuickSight to connect to Amazon Redshift.
    - [ ] D. Create a new security group for Amazon Redshift in us-east-1 with an inbound rule authorizing access from the appropriate IP address range for the Amazon QuickSight servers in ap-northeast-1.
    <details>
       <summary>Answer</summary>

       D.

    </details>

15. An airline has .csv-formatted data stored in Amazon S3 with an AWS Glue Data Catalog. Data analysts want to join this data with call center data stored in Amazon Redshift as part of a dally batch process. The Amazon Redshift cluster is already under a heavy load. The solution must be managed, serverless, well- functioning, and minimize the load on the existing Amazon Redshift cluster. The solution should also require minimal effort and development activity. Which solution meets these requirements?
    - [ ] A. Unload the call center data from Amazon Redshift to Amazon S3 using an AWS Lambda function. Perform the join with AWS Glue ETL scripts.
    - [ ] B. Export the call center data from Amazon Redshift using a Python shell in AWS Glue. Perform the join with AWS Glue ETL scripts.
    - [ ] C. Create an external table using Amazon Redshift Spectrum for the call center data and perform the join with Amazon Redshift.
    - [ ] D. Export the call center data from Amazon Redshift to Amazon EMR using Apache Sqoop. Perform the join with Apache Hive.
    <details>
       <summary>Answer</summary>

       C.

    </details>

16. A data analyst is using Amazon QuickSight for data visualization across multiple datasets generated by applications. Each application stores files within a separate Amazon S3 bucket. AWS Glue Data Catalog is used as a central catalog across all application data in Amazon S3. A new application stores its data within a separate S3 bucket. After updating the catalog to include the new application data source, the data analyst created a new Amazon QuickSight data source from an Amazon Athena table, but the import into SPICE failed. How should the data analyst resolve the issue?
    - [ ] A. Edit the permissions for the AWS Glue Data Catalog from within the Amazon QuickSight console.
    - [ ] B. Edit the permissions for the new S3 bucket from within the Amazon QuickSight console.
    - [ ] C. Edit the permissions for the AWS Glue Data Catalog from within the AWS Glue console.
    - [ ] D. Edit the permissions for the new S3 bucket from within the S3 console.

    <details>
       <summary>Answer</summary>

       B.

    </details>

17. A team of data scientists plans to analyze market trend data for their company's new investment strategy. The trend data comes from five different data sources in large volumes. The team wants to utilize Amazon Kinesis to support their use case. The team uses SQL-like queries to analyze trends and wants to send notifications based on certain significant patterns in the trends. Additionally, the data scientists want to save the data to Amazon S3 for archival and historical re- processing, and use AWS managed services wherever possible. The team wants to implement the lowest-cost solution. Which solution meets these requirements?
    - [ ] A. Publish data to one Kinesis data stream. Deploy a custom application using the Kinesis Client Library (KCL) for analyzing trends, and send notifications using Amazon SNS. Configure Kinesis Data Firehose on the Kinesis data stream to persist data to an S3 bucket.
    - [ ] B. Publish data to one Kinesis data stream. Deploy Kinesis Data Analytic to the stream for analyzing trends, and configure an AWS Lambda function as an output to send notifications using Amazon SNS. Configure Kinesis Data Firehose on the Kinesis data stream to persist data to an S3 bucket.
    - [ ] C. Publish data to two Kinesis data streams. Deploy Kinesis Data Analytics to the first stream for analyzing trends, and configure an AWS Lambda function as an output to send notifications using Amazon SNS. Configure Kinesis Data Firehose on the second Kinesis data stream to persist data to an S3 bucket.
    - [ ] D. Publish data to two Kinesis data streams. Deploy a custom application using the Kinesis Client Library (KCL) to the first stream for analyzing trends, and send notifications using Amazon SNS. Configure Kinesis Data Firehose on the second Kinesis data stream to persist data to an S3 bucket.

    <details>
       <summary>Answer</summary>

       B.

    </details>

18. A company currently uses Amazon Athena to query its global datasets. The regional data is stored in Amazon S3 in the us-east-1 and us-west-2 Regions. The data is not encrypted. To simplify the query process and manage it centrally, the company wants to use Athena in us-west-2 to query data from Amazon S3 in both Regions. The solution should be as low-cost as possible. What should the company do to achieve this goal?
    - [ ] A. Use AWS DMS to migrate the AWS Glue Data Catalog from us-east-1 to us-west-2. Run Athena queries in us-west-2.
    - [ ] B. Run the AWS Glue crawler in us-west-2 to catalog datasets in all Regions. Once the data is crawled, run Athena queries in us-west-2.
    - [ ] C. Enable cross-Region replication for the S3 buckets in us-east-1 to replicate data in us-west-2. Once the data is replicated in us-west-2, run the AWS Glue crawler there to update the AWS Glue Data Catalog in us-west-2 and run Athena queries.
    - [ ] D. Update AWS Glue resource policies to provide us-east-1 AWS Glue Data Catalog access to us-west-2. Once the catalog in us-west-2 has access to the catalog in us-east-1, run Athena queries in us-west-2.

    <details>
       <summary>Answer</summary>

       B.

    </details>

19. A large company receives files from external parties in Amazon EC2 throughout the day. At the end of the day, the files are combined into a single file, compressed into a gzip file, and uploaded to Amazon S3. The total size of all the files is close to 100 GB daily. Once the files are uploaded to Amazon S3, an AWS Batch program executes a COPY command to load the files into an Amazon Redshift cluster. Which program modification will accelerate the COPY process?
    - [ ] A. Upload the individual files to Amazon S3 and run the COPY command as soon as the files become available.
    - [ ] B. Split the number of files so they are equal to a multiple of the number of slices in the Amazon Redshift cluster. Gzip and upload the files to Amazon S3. Run the COPY command on the files.
    - [ ] C. Split the number of files so they are equal to a multiple of the number of compute nodes in the Amazon Redshift cluster. Gzip and upload the files to Amazon S3. Run the COPY command on the files.
    - [ ] D. Apply sharding by breaking up the files so the distkey columns with the same values go to the same file. Gzip and upload the sharded files to Amazon S3. Run the COPY command on the files.

    <details>
       <summary>Answer</summary>

       B.

    </details>

20. A large ride-sharing company has thousands of drivers globally serving millions of unique customers every day. The company has decided to migrate an existing data mart to Amazon Redshift. The existing schema includes the following tables. ✑ A trips fact table for information on completed rides. ✑ A drivers dimension table for driver profiles. ✑ A customers fact table holding customer profile information. The company analyzes trip details by date and destination to examine profitability by region. The drivers data rarely changes. The customers data frequently changes. What table design provides optimal query performance?
    - [ ] A. Use DISTSTYLE KEY (destination) for the trips table and sort by date. Use DISTSTYLE ALL for the drivers and customers tables.
    - [ ] B. Use DISTSTYLE EVEN for the trips table and sort by date. Use DISTSTYLE ALL for the drivers table. Use DISTSTYLE EVEN for the customers table.
    - [ ] C. Use DISTSTYLE KEY (destination) for the trips table and sort by date. Use DISTSTYLE ALL for the drivers table. Use DISTSTYLE EVEN for the customers table.
    - [ ] D. Use DISTSTYLE EVEN for the drivers table and sort by date. Use DISTSTYLE ALL for both fact tables.
    <details>
       <summary>Answer</summary>

       C.

    </details>

21. Three teams of data analysts use Apache Hive on an Amazon EMR cluster with the EMR File System (EMRFS) to query data stored within each teams Amazon S3 bucket. The EMR cluster has Kerberos enabled and is configured to authenticate users from the corporate Active Directory. The data is highly sensitive, so access must be limited to the members of each team. Which steps will satisfy the security requirements?
    - [ ] A. For the EMR cluster Amazon EC2 instances, create a service role that grants no access to Amazon S3. Create three additional IAM roles, each granting access to each team's specific bucket. Add the additional IAM roles to the cluster's EMR role for the EC2 trust policy. Create a security configuration mapping for the additional IAM roles to Active Directory user groups for each team.
    - [ ] B. For the EMR cluster Amazon EC2 instances, create a service role that grants no access to Amazon S3. Create three additional IAM roles, each granting access to each team's specific bucket. Add the service role for the EMR cluster EC2 instances to the trust policies for the additional IAM roles. Create a security configuration mapping for the additional IAM roles to Active Directory user groups for each team.
    - [ ] C. For the EMR cluster Amazon EC2 instances, create a service role that grants full access to Amazon S3. Create three additional IAM roles, each granting access to each team's specific bucket. Add the service role for the EMR cluster EC2 instances to the trust polices for the additional IAM roles. Create a security configuration mapping for the additional IAM roles to Active Directory user groups for each team.
    - [ ] D. For the EMR cluster Amazon EC2 instances, create a service role that grants full access to Amazon S3. Create three additional IAM roles, each granting access to each team's specific bucket. Add the service role for the EMR cluster EC2 instances to the trust polices for the base IAM roles. Create a security configuration mapping for the additional IAM roles to Active Directory user groups for each team.

    <details>
       <summary>Answer</summary>

       B.

    </details>

22. A company is planning to create a data lake in Amazon S3. The company wants to create tiered storage based on access patterns and cost objectives. The solution must include support for JDBC connections from legacy clients, metadata management that allows federation for access control, and batch-based ETL using PySpark and Scala. Operational management should be limited. Which combination of components can meet these requirements? (Choose three.)
    - [ ] A. AWS Glue Data Catalog for metadata management
    - [ ] B. Amazon EMR with Apache Spark for ETL
    - [ ] C. AWS Glue for Scala-based ETL
    - [ ] D. Amazon EMR with Apache Hive for JDBC clients
    - [ ] E. Amazon Athena for querying data in Amazon S3 using JDBC drivers
    - [ ] F. Amazon EMR with Apache Hive, using an Amazon RDS with MySQL-compatible backed metastore
  
    <details>
       <summary>Answer</summary>

       ACE.

    </details>

23. A company wants to optimize the cost of its data and analytics platform. The company is ingesting a number of .csv and JSON files in Amazon S3 from various data sources. Incoming data is expected to be 50 GB each day. The company is using Amazon Athena to query the raw data in Amazon S3 directly. Most queries aggregate data from the past 12 months, and data that is older than 5 years is infrequently queried. The typical query scans about 500 MB of data and is expected to return results in less than 1 minute. The raw data must be retained indefinitely for compliance requirements. Which solution meets the company's requirements?
    - [ ] A. Use an AWS Glue ETL job to compress, partition, and convert the data into a columnar data format. Use Athena to query the processed dataset. Configure a lifecycle policy to move the processed data into the Amazon S3 Standard-Infrequent Access (S3 Standard-IA) storage class 5 years after object creation. Configure a second lifecycle policy to move the raw data into Amazon S3 Glacier for long-term archival 7 days after object creation.
    - [ ] B. Use an AWS Glue ETL job to partition and convert the data into a row-based data format. Use Athena to query the processed dataset. Configure a lifecycle policy to move the data into the Amazon S3 Standard-Infrequent Access (S3 Standard-IA) storage class 5 years after object creation. Configure a second lifecycle policy to move the raw data into Amazon S3 Glacier for long-term archival 7 days after object creation.
    - [ ] C. Use an AWS Glue ETL job to compress, partition, and convert the data into a columnar data format. Use Athena to query the processed dataset. Configure a lifecycle policy to move the processed data into the Amazon S3 Standard-Infrequent Access (S3 Standard-IA) storage class 5 years after the object was last accessed. Configure a second lifecycle policy to move the raw data into Amazon S3 Glacier for long-term archival 7 days after the last date the object was accessed.
    - [ ] D. Use an AWS Glue ETL job to partition and convert the data into a row-based data format. Use Athena to query the processed dataset. Configure a lifecycle policy to move the data into the Amazon S3 Standard-Infrequent Access (S3 Standard-IA) storage class 5 years after the object was last accessed. Configure a second lifecycle policy to move the raw data into Amazon S3 Glacier for long-term archival 7 days after the last date the object was accessed.

    <details>
       <summary>Answer</summary>

       A.

    </details>

24. A regional energy company collects voltage data from sensors attached to buildings. To address any known dangerous conditions, the company wants to be alerted when a sequence of two voltage drops is detected within 10 minutes of a voltage spike at the same building. It is important to ensure that all messages are delivered as quickly as possible. The system must be fully managed and highly available. The company also needs a solution that will automatically scale up as it covers additional cites with this monitoring feature. The alerting system is subscribed to an Amazon SNS topic for remediation. Which solution meets these requirements?
    - [ ] A. Create an Amazon Managed Streaming for Kafka cluster to ingest the data, and use an Apache Spark Streaming with Apache Kafka consumer API in an automatically scaled Amazon EMR cluster to process the incoming data. Use the Spark Streaming application to detect the known event sequence and send the SNS message.
    - [ ] B. Create a REST-based web service using Amazon API Gateway in front of an AWS Lambda function. Create an Amazon RDS for PostgreSQL database with sufficient Provisioned IOPS (PIOPS). In the Lambda function, store incoming events in the RDS database and query the latest data to detect the known event sequence and send the SNS message.
    - [ ] C. Create an Amazon Kinesis Data Firehose delivery stream to capture the incoming sensor data. Use an AWS Lambda transformation function to detect the known event sequence and send the SNS message.
    - [ ] D. Create an Amazon Kinesis data stream to capture the incoming sensor data and create another stream for alert messages. Set up AWS Application Auto Scaling on both. Create a Kinesis Data Analytics for Java application to detect the known event sequence, and add a message to the message stream. Configure an AWS Lambda function to poll the message stream and publish to the SNS topic.

    <details>
       <summary>Answer</summary>

       D.

    </details>

25. An ecommerce company stores customer purchase data in Amazon RDS. The company wants a solution to store and analyze historical data. The most recent 6 months of data will be queried frequently for analytics workloads. This data is several terabytes large. Once a month, historical data for the last 5 years must be accessible and will be joined with the more recent data. The company wants to optimize performance and cost. Which storage solution will meet these requirements?
    - [ ] A. Create a read replica of the RDS database to store the most recent 6 months of data. Copy the historical data into Amazon S3. Create an AWS Glue Data Catalog of the data in Amazon S3 and Amazon RDS. Run historical queries using Amazon Athena.
    - [ ] B. Use an ETL tool to incrementally load the most recent 6 months of data into an Amazon Redshift cluster. Run more frequent queries against this cluster. Create a read replica of the RDS database to run queries on the historical data.
    - [ ] C. Incrementally copy data from Amazon RDS to Amazon S3. Create an AWS Glue Data Catalog of the data in Amazon S3. Use Amazon Athena to query the data.
    - [ ] D. Incrementally copy data from Amazon RDS to Amazon S3. Load and store the most recent 6 months of data in Amazon Redshift. Configure an Amazon Redshift Spectrum table to connect to all historical data.

    <details>
       <summary>Answer</summary>

       C.

    </details>

26. A media content company has a streaming playback application. The company wants to collect and analyze the data to provide near-real-time feedback on playback issues. The company needs to consume this data and return results within 30 seconds according to the service-level agreement (SLA). The company needs the consumer to identify playback issues, such as quality during a specified timeframe. The data will be emitted as JSON and may change schemas over time. Which solution will allow the company to collect data for processing while meeting these requirements?
    - [ ] A. Send the data to Amazon Kinesis Data Firehose with delivery to Amazon S3. Configure an S3 event trigger an AWS Lambda function to process the data. The Lambda function will consume the data and process it to identify potential playback issues. Persist the raw data to Amazon S3.
    - [ ] B. Send the data to Amazon Managed Streaming for Kafka and configure an Amazon Kinesis Analytics for Java application as the consumer. The application will consume the data and process it to identify potential playback issues. Persist the raw data to Amazon DynamoDB.
    - [ ] C. Send the data to Amazon Kinesis Data Firehose with delivery to Amazon S3. Configure Amazon S3 to trigger an event for AWS Lambda to process. The Lambda function will consume the data and process it to identify potential playback issues. Persist the raw data to Amazon DynamoDB.
    - [ ] D. Send the data to Amazon Kinesis Data Streams and configure an Amazon Kinesis Analytics for Java application as the consumer. The application will consume the data and process it to identify potential playback issues. Persist the raw data to Amazon S3.

    <details>
       <summary>Answer</summary>

       - Requirement Analysis:
         - Near-real-time feedback: The solution needs to process and analyze data quickly (within 30 seconds as per the SLA).
         - Data Source: Data will be in JSON format and may have changing schemas.
         - Purpose: Identify playback issues like quality during a specified timeframe.
       - Option A:
         - Kinesis Data Firehose to S3: Efficient for data ingestion and storage but may not support near-real-time analysis because of potential delays in S3 event triggering and processing.
         - Lambda for Processing: Good for real-time processing but might face cold start issues and have limitations in execution time and memory, which can affect meeting the SLA.
         - Data Persisted to S3: Suitable for storing raw data.
       - Option B:
         - Kafka and Kinesis Analytics for Java: Kafka is powerful for real-time data streaming, and Kinesis Analytics is suitable for real-time analytics, but the setup can be complex.
         - Data Persisted to DynamoDB: DynamoDB is fast for reads/writes but might be overkill for merely storing raw data and can be costlier than S3 for large volumes of data.
       - Option C:
         - Similar to Option A but with data persistence to DynamoDB, which may not be optimal for just storing large volumes of raw data.
       - Option D:
         - Kinesis Data Streams and Kinesis Analytics for Java: Kinesis Data Streams is excellent for real-time data streaming, and Kinesis Analytics is ideal for real-time analytics.
         - Data Persisted to S3: Efficient and cost-effective for storing large volumes of raw data.
       - Answer: D

    </details>

27. A company leverages Amazon Athena for ad-hoc queries against data stored in Amazon S3. The company wants to implement additional controls to separate query execution and query history among users, teams, or applications running in the same AWS account to comply with internal security policies. Which solution meets these requirements?
    - [ ] A. Create an S3 bucket for each given use case, create an S3 bucket policy that grants permissions to appropriate individual IAM users. and apply the S3 bucket policy to the S3 bucket.
    - [ ] B. Create an Athena workgroup for each given use case, apply tags to the workgroup, and create an IAM policy using the tags to apply appropriate permissions to the workgroup.
    - [ ] C. Create an IAM role for each given use case, assign appropriate permissions to the role for the given use case, and add the role to associate the role with Athena.
    - [ ] D. Create an AWS Glue Data Catalog resource policy for each given use case that grants permissions to appropriate individual IAM users, and apply the resource policy to the specific tables used by Athena.

    <details>
       <summary>Answer</summary>

       B.

    </details>

28. A company wants to use an automatic machine learning (ML) Random Cut Forest (RCF) algorithm to visualize complex real-world scenarios, such as detecting seasonality and trends, excluding outers, and imputing missing values. The team working on this project is non-technical and is looking for an out-of-the-box solution that will require the LEAST amount of management overhead. Which solution will meet these requirements?
    - [ ] A. Use an AWS Glue ML transform to create a forecast and then use Amazon QuickSight to visualize the data.
    - [ ] B. Use Amazon QuickSight to visualize the data and then use ML-powered forecasting to forecast the key business metrics.
    - [ ] C. Use a pre-build ML AMI from the AWS Marketplace to create forecasts and then use Amazon QuickSight to visualize the data.
    - [ ] D. Use calculated fields to create a new forecast and then use Amazon QuickSight to visualize the data.

    <details>
       <summary>Answer</summary>

       B.

    </details>

29. A retail company's data analytics team recently created multiple product sales analysis dashboards for the average selling price per product using Amazon QuickSight. The dashboards were created from .csv files uploaded to Amazon S3. The team is now planning to share the dashboards with the respective external product owners by creating individual users in Amazon QuickSight. For compliance and governance reasons, restricting access is a key requirement. The product owners should view only their respective product analysis in the dashboard reports. Which approach should the data analytics team take to allow product owners to view only their products in the dashboard?
    - [ ] A. Separate the data by product and use S3 bucket policies for authorization.
    - [ ] B. Separate the data by product and use IAM policies for authorization.
    - [ ] C. Create a manifest file with row-level security.
    - [ ] D. Create dataset rules with row-level security.

    <details>
       <summary>Answer</summary>

       D.

    </details>

30. A company has developed an Apache Hive script to batch process data stared in Amazon S3. The script needs to run once every day and store the output in Amazon S3. The company tested the script, and it completes within 30 minutes on a small local three-node cluster. Which solution is the MOST cost-effective for scheduling and executing the script?
    - [ ] A. Create an AWS Lambda function to spin up an Amazon EMR cluster with a Hive execution step. Set KeepJobFlowAliveWhenNoSteps to false and disable the termination protection flag. Use Amazon CloudWatch Events to schedule the Lambda function to run daily.
    - [ ] B. Use the AWS Management Console to spin up an Amazon EMR cluster with Python Hue. Hive, and Apache Oozie. Set the termination protection flag to true and use Spot Instances for the core nodes of the cluster. Configure an Oozie workflow in the cluster to invoke the Hive script daily.
    - [ ] C. Create an AWS Glue job with the Hive script to perform the batch operation. Configure the job to run once a day using a time-based schedule.
    - [ ] D. Use AWS Lambda layers and load the Hive runtime to AWS Lambda and copy the Hive script. Schedule the Lambda function to run daily by creating a workflow using AWS Step Functions.

    <details>
       <summary>Answer</summary>

       A.

    </details>

31. A company wants to improve the data load time of a sales data dashboard. Data has been collected as .csv files and stored within an Amazon S3 bucket that is partitioned by date. The data is then loaded to an Amazon Redshift data warehouse for frequent analysis. The data volume is up to 500 GB per day. Which solution will improve the data loading performance?
    - [ ] A. Compress .csv files and use an INSERT statement to ingest data into Amazon Redshift.
    - [ ] B. Split large .csv files, then use a COPY command to load data into Amazon Redshift.
    - [ ] C. Use Amazon Kinesis Data Firehose to ingest data into Amazon Redshift.
    - [ ] D. Load the .csv files in an unsorted key order and vacuum the table in Amazon Redshift.

    <details>
       <summary>Answer</summary>

       B.

    </details>

32. A company has a data warehouse in Amazon Redshift that is approximately 500 TB in size. New data is imported every few hours and read-only queries are run throughout the day and evening. There is a particularly heavy load with no writes for several hours each morning on business days. During those hours, some queries are queued and take a long time to execute. The company needs to optimize query execution and avoid any downtime. What is the MOST cost-effective solution?
    - [ ] A. Enable concurrency scaling in the workload management (WLM) queue.
    - [ ] B. Add more nodes using the AWS Management Console during peak hours. Set the distribution style to ALL.
    - [ ] C. Use elastic resize to quickly add nodes during peak times. Remove the nodes when they are not needed.
    - [ ] D. Use a snapshot, restore, and resize operation. Switch to the new target cluster.

    <details>
       <summary>Answer</summary>

       A.

    </details>

33. A company analyzes its data in an Amazon Redshift data warehouse, which currently has a cluster of three dense storage nodes. Due to a recent business acquisition, the company needs to load an additional 4 TB of user data into Amazon Redshift. The engineering team will combine all the user data and apply complex calculations that require I/O intensive resources. The company needs to adjust the cluster's capacity to support the change in analytical and storage requirements. Which solution meets these requirements?
    - [ ] A. Resize the cluster using elastic resize with dense compute nodes.
    - [ ] B. Resize the cluster using classic resize with dense compute nodes.
    - [ ] C. Resize the cluster using elastic resize with dense storage nodes.
    - [ ] D. Resize the cluster using classic resize with dense storage nodes.

    <details>
       <summary>Answer</summary>

       - Node Types:
         - Dense Compute Nodes (DC): Optimized for performance-intensive workloads, providing fast CPU performance and high I/O operations. However, they offer less storage capacity compared to dense storage nodes.
         - Dense Storage Nodes (DS): Optimized for large data workloads, offering a high storage capacity but with potentially lower performance compared to dense compute nodes.
       - Resize Methods:
         - Elastic Resize: Quickly adds or removes nodes to the cluster, resulting in minimal downtime. However, it only works within the same node type (either all DC or all DS).
         - Classic Resize: Involves a full copy of data to a new cluster with a different configuration, resulting in a longer downtime but allows switching between node types.
       - Requirement Analysis:
         - The company needs to load an additional 4 TB of user data.
         - The team requires more I/O intensive resources for complex calculations.
         - The current setup uses three dense storage nodes.
       - Option Evaluation:
         - Option A (Elastic Resize with DC Nodes): Offers improved I/O performance but might not be optimal for storage capacity, considering an additional 4 TB of data needs to be accommodated.
         - Option B (Classic Resize with DC Nodes): Switches to compute-optimized nodes, enhancing I/O performance for complex calculations, but may compromise on storage capacity for the additional data.
         - Option C (Elastic Resize with DS Nodes): Increases storage capacity while maintaining the current dense storage node configuration, but may not significantly enhance I/O performance.
         - Option D (Classic Resize with DS Nodes): Increases storage capacity and maintains the dense storage node type, possibly providing a better balance between storage needs and I/O performance.
       - Recommendation:
         - Given the need for both additional storage (4 TB) and enhanced I/O performance for complex calculations, Option D (Classic Resize with Dense Storage Nodes) seems the most balanced choice. It allows for an increase in storage capacity while potentially offering better I/O performance than the existing setup. Classic resize also enables changing the configuration more flexibly, which could be beneficial in adjusting the cluster to the new business requirements.

    </details>

34. A company stores its sales and marketing data that includes personally identifiable information (PII) in Amazon S3. The company allows its analysts to launch their own Amazon EMR cluster and run analytics reports with the data. To meet compliance requirements, the company must ensure the data is not publicly accessible throughout this process. A data engineer has secured Amazon S3 but must ensure the individual EMR clusters created by the analysts are not exposed to the public internet. Which solution should the data engineer to meet this compliance requirement with LEAST amount of effort?
    - [ ] A. Create an EMR security configuration and ensure the security configuration is associated with the EMR clusters when they are created.
    - [ ] B. Check the security group of the EMR clusters regularly to ensure it does not allow inbound traffic from IPv4 0.0.0.0/0 or IPv6 ::/0.
    - [ ] C. Enable the block public access setting for Amazon EMR at the account level before any EMR cluster is created.
    - [ ] D. Use AWS WAF to block public internet access to the EMR clusters across the board.

    <details>
       <summary>Answer</summary>

       C.

    </details>

35. A company's marketing team has asked for help in identifying a high performing long-term storage service for their data based on the following requirements: ✑ The data size is approximately 32 TB uncompressed. ✑ There is a low volume of single-row inserts each day. ✑ There is a high volume of aggregation queries each day. ✑ Multiple complex joins are performed. ✑ The queries typically involve a small subset of the columns in a table. Which storage service will provide the MOST performant solution?
    - [ ] A. Amazon Aurora MySQL
    - [ ] B. Amazon Redshift
    - [ ] C. Amazon Neptune
    - [ ] D. Amazon Elasticsearch

    <details>
       <summary>Answer</summary>

       B.

    </details>

36. A financial company uses Amazon S3 as its data lake and has set up a data warehouse using a multi-node Amazon Redshift cluster. The data files in the data lake are organized in folders based on the data source of each data file. All the data files are loaded to one table in the Amazon Redshift cluster using a separate COPY command for each data file location. With this approach, loading all the data files into Amazon Redshift takes a long time to complete. Users want a faster solution with little or no increase in cost while maintaining the segregation of the data files in the S3 data lake. Which solution meets these requirements?
    - [ ] A. Use Amazon EMR to copy all the data files into one folder and issue a COPY command to load the data into Amazon Redshift.
    - [ ] B. Load all the data files in parallel to Amazon Aurora, and run an AWS Glue job to load the data into Amazon Redshift.
    - [ ] C. Use an AWS Glue job to copy all the data files into one folder and issue a COPY command to load the data into Amazon Redshift.
    - [ ] D. Create a manifest file that contains the data file locations and issue a COPY command to load the data into Amazon Redshift.

    <details>
       <summary>Answer</summary>

       D.

    </details>

37. A technology company is creating a dashboard that will visualize and analyze time-sensitive data. The data will come in through Amazon Kinesis Data Firehose with the butter interval set to 60 seconds. The dashboard must support near-real-time data. Which visualization solution will meet these requirements?
    - [ ] A. Select Amazon Elasticsearch Service (Amazon ES) as the endpoint for Kinesis Data Firehose. Set up a Kibana dashboard using the data in Amazon ES with the desired analyses and visualizations.
    - [ ] B. Select Amazon S3 as the endpoint for Kinesis Data Firehose. Read data into an Amazon SageMaker Jupyter notebook and carry out the desired analyses and visualizations.
    - [ ] C. Select Amazon Redshift as the endpoint for Kinesis Data Firehose. Connect Amazon QuickSight with SPICE to Amazon Redshift to create the desired analyses and visualizations.
    - [ ] D. Select Amazon S3 as the endpoint for Kinesis Data Firehose. Use AWS Glue to catalog the data and Amazon Athena to query it. Connect Amazon QuickSight with SPICE to Athena to create the desired analyses and visualizations.

    <details>
       <summary>Answer</summary>

       A.

    </details>

38. A financial company uses Apache Hive on Amazon EMR for ad-hoc queries. Users are complaining of sluggish performance. A data analyst notes the following: ✑ Approximately 90% of queries are submitted 1 hour after the market opens. Hadoop Distributed File System (HDFS) utilization never exceeds 10%. Which solution would help address the performance issues?
    - [ ] A. Create instance fleet configurations for core and task nodes. Create an automatic scaling policy to scale out the instance groups based on the Amazon CloudWatch CapacityRemainingGB metric. Create an automatic scaling policy to scale in the instance fleet based on the CloudWatch CapacityRemainingGB metric.
    - [ ] B. Create instance fleet configurations for core and task nodes. Create an automatic scaling policy to scale out the instance groups based on the Amazon CloudWatch YARNMemoryAvailablePercentage metric. Create an automatic scaling policy to scale in the instance fleet based on the CloudWatch YARNMemoryAvailablePercentage metric.
    - [ ] C. Create instance group configurations for core and task nodes. Create an automatic scaling policy to scale out the instance groups based on the Amazon CloudWatch CapacityRemainingGB metric. Create an automatic scaling policy to scale in the instance groups based on the CloudWatch CapacityRemainingGB metric.
    - [ ] D. Create instance group configurations for core and task nodes. Create an automatic scaling policy to scale out the instance groups based on the Amazon CloudWatch YARNMemoryAvailablePercentage metric. Create an automatic scaling policy to scale in the instance groups based on the CloudWatch YARNMemoryAvailablePercentage metric.

    <details>
       <summary>Answer</summary>

       D.

    </details>

39. A media company has been performing analytics on log data generated by its applications. There has been a recent increase in the number of concurrent analytics jobs running, and the overall performance of existing jobs is decreasing as the number of new jobs is increasing. The partitioned data is stored in Amazon S3 One Zone-Infrequent Access (S3 One Zone-IA) and the analytic processing is performed on Amazon EMR clusters using the EMR File System (EMRFS) with consistent view enabled. A data analyst has determined that it is taking longer for the EMR task nodes to list objects in Amazon S3. Which action would MOST likely increase the performance of accessing log data in Amazon S3?
    - [ ] A. Use a hash function to create a random string and add that to the beginning of the object prefixes when storing the log data in Amazon S3.
    - [ ] B. Use a lifecycle policy to change the S3 storage class to S3 Standard for the log data.
    - [ ] C. Increase the read capacity units (RCUs) for the shared Amazon DynamoDB table.
    - [ ] D. Redeploy the EMR clusters that are running slowly to a different Availability Zone.

    <details>
       <summary>Answer</summary>

       C.

    </details>

40. A company has developed several AWS Glue jobs to validate and transform its data from Amazon S3 and load it into Amazon RDS for MySQL in batches once every day. The ETL jobs read the S3 data using a DynamicFrame. Currently, the ETL developers are experiencing challenges in processing only the incremental data on every run, as the AWS Glue job processes all the S3 input data on each run. Which approach would allow the developers to solve the issue with minimal coding effort?
    - [ ] A. Have the ETL jobs read the data from Amazon S3 using a DataFrame.
    - [ ] B. Enable job bookmarks on the AWS Glue jobs.
    - [ ] C. Create custom logic on the ETL jobs to track the processed S3 objects.
    - [ ] D. Have the ETL jobs delete the processed objects or data from Amazon S3 after each run.

    <details>
       <summary>Answer</summary>

       B.

    </details>

41. A developer is building a web application that uses Amazon API Gateway to expose an AWS Lambda function to process requests from clients. During testing, the developer notices that the API Gateway times out even though the Lambda function finishes under the set time limit. Which of the following API Gateway metrics in Amazon CloudWatch can help the developer troubleshoot the issue? (Choose two.)
    - [ ] A. CacheHitCount
    - [ ] B. IntegrationLatency
    - [ ] C. CacheMissCount
    - [ ] D. Latency
    - [ ] E. Count

    <details>
       <summary>Answer</summary>

       BD.

    </details>

42. A Developer is designing an AWS Lambda function that create temporary files that are less than 10 MB during execution. The temporary files will be accessed and modified multiple times during execution. The Developer has no need to save or retrieve these files in the future. Where should the temporary file be stored?
    - [ ] A. the /tmp directory
    - [ ] B. Amazon EFS
    - [ ] C. Amazon EBS
    - [ ] D. Amazon S3

    <details>
       <summary>Answer</summary>

       A.

    </details>

43. A developer is designing a serverless application with two AWS Lambda functions to process photos. One Lambda function stores objects in an Amazon S3 bucket and stores the associated metadata in an Amazon DynamoDB table. The other Lambda function fetches the objects from the S3 bucket by using the metadata from the DynamoDB table. Both Lambda functions use the same Python library to perform complex computations and are approaching the quota for the maximum size of zipped deployment packages. What should the developer do to reduce the size of the Lambda deployment packages with the LEAST operational overhead?
    - [ ] A. Package each Python library in its own .zip file archive. Deploy each Lambda function with its own copy of the library.
    - [ ] B. Create a Lambda layer with the required Python library. Use the Lambda layer in both Lambda functions.
    - [ ] C. Combine the two Lambda functions into one Lambda function. Deploy the Lambda function as a single .zip file archive.
    - [ ] D. Download the Python library to an S3 bucket. Program the Lambda functions to reference the object URLs.

    <details>
       <summary>Answer</summary>

       B.
       Lambda layers are used to store the code dependencies, custom runtimes, configuration files etc. We create a .zip file archive that contains supplementary code or data.

    </details>

44. A developer is writing an AWS Lambda function. The developer wants to log key events that occur while the Lambda function runs. The developer wants to include a unique identifier to associate the events with a specific function invocation. The developer adds the following code to the Lambda function: Which solution will meet this requirement?

    ```javascript
    function handler (event, context) {

    } 
    ```

    - [ ] A. Obtain the request identifier from the AWS request ID field in the context object. Configure the application to write logs to standard output.
    - [ ] B. Obtain the request identifier from the AWS request ID field in the event object. Configure the application to write logs to a file.
    - [ ] C. Obtain the request identifier from the AWS request ID field in the event object. Configure the application to write logs to standard output.
    - [ ] D. Obtain the request identifier from the AWS request ID field in the context object. Configure the application to write logs to a file.

    <details>
       <summary>Answer</summary>

       A.
       In AWS Lambda, each invocation has a unique identifier called the "request ID." This request ID is accessible through the context object and not the event object. So, let's break down the options:
       - Option A: This aligns with how AWS Lambda works since Lambda captures logs written to standard output and sends them to Amazon CloudWatch Logs.
       - Option B: suggests obtaining the request identifier from the AWS request ID field in the event object, but this is incorrect because the request ID is in the context object, not the event object.
       - Option C: has the same flaw as Option B, suggesting obtaining the request ID from the event object.
       - Option D: suggests obtaining the request ID from the context object but then writing logs to a file. Lambda functions log to CloudWatch by writing to standard output or standard error, not to files.

    </details>

45. An application uses an Amazon EC2 Auto Scaling group. A developer notices that EC2 instances are taking a long time to become available during scale-out events. The UserData script is taking a long time to run. The developer must implement a solution to decrease the time that elapses before an EC2 instance becomes available. The solution must make the most recent version of the application available at all times and must apply all available security updates. The solution also must minimize the number of images that are created. The images must be validated. Which combination of steps should the developer take to meet these requirements? (Choose two.)
    - [ ] A. Use EC2 Image Builder to create an Amazon Machine Image (AMI). Install all the patches and agents that are needed to manage and run the application. Update the Auto Scaling group launch configuration to use the AMI.
    - [ ] B. Use EC2 Image Builder to create an Amazon Machine Image (AMI). Install the latest version of the application and all the patches and agents that are needed to manage and run the application. Update the Auto Scaling group launch configuration to use the AMI.
    - [ ] C. Set up AWS CodeDeploy to deploy the most recent version of the application at runtime.
    - [ ] D. Set up AWS CodePipeline to deploy the most recent version of the application at runtime.
    - [ ] E. Remove any commands that perform operating system patching from the UserData script.

    <details>
       <summary>Answer</summary>

       BC.

    </details>

46. A developer is creating an AWS Lambda function that needs credentials to connect to an Amazon RDS for MySQL database. An Amazon S3 bucket currently stores the credentials. The developer needs to improve the existing solution by implementing credential rotation and secure storage. The developer also needs to provide integration with the Lambda function. Which solution should the developer use to store and retrieve the credentials with the LEAST management overhead?
    - [ ] A. Store the credentials in AWS Systems Manager Parameter Store. Select the database that the parameter will access. Use the default AWS Key Management Service (AWS KMS) key to encrypt the parameter. Enable automatic rotation for the parameter. Use the parameter from Parameter Store on the Lambda function to connect to the database.
    - [ ] B. Encrypt the credentials with the default AWS Key Management Service (AWS KMS) key. Store the credentials as environment variables for the Lambda function. Create a second Lambda function to generate new credentials and to rotate the credentials by updating the environment variables of the first Lambda function. Invoke the second Lambda function by using an Amazon EventBridge rule that runs on a schedule. Update the database to use the new credentials. On the first Lambda function, retrieve the credentials from the environment variables. Decrypt the credentials by using AWS KMS, Connect to the database.
    - [ ] C. Store the credentials in AWS Secrets Manager. Set the secret type to Credentials for Amazon RDS database. Select the database that the secret will access. Use the default AWS Key Management Service (AWS KMS) key to encrypt the secret. Enable automatic rotation for the secret. Use the secret from Secrets Manager on the Lambda function to connect to the database.
    - [ ] D. Encrypt the credentials by using AWS Key Management Service (AWS KMS). Store the credentials in an Amazon DynamoDB table. Create a second Lambda function to rotate the credentials. Invoke the second Lambda function by using an Amazon EventBridge rule that runs on a schedule. Update the DynamoDB table. Update the database to use the generated credentials. Retrieve the credentials from DynamoDB with the first Lambda function. Connect to the database.

    <details>
       <summary>Answer</summary>

       C.

    </details>

47. A developer has written the following IAM policy to provide access to an Amazon S3 bucket: Which access does the policy allow regarding the s3:GetObject and s3:PutObject actions?

    ```json
    {
      "Version":  "2012-10-17",
      "Statements": [
         {
            "Effect": "Allow",
            "Action": [
               "s3:GetObject",
               "s3:PutObject"
            ],
            "Resource": "arn:aws:s3:::DOC-EXAMPLE-BUCKET/*"
         },
         {
            "Effect": "Deny",
            "Action": "s3:*",
            "Resource": "arn:aws:s3:::DOC-EXAMPLE-BUCKET/*"
         }
      ]
    }
    ```

    - [ ] A. Access on all buckets except the “DOC-EXAMPLE-BUCKET” bucket
    - [ ] B. Access on all buckets that start with “DOC-EXAMPLE-BUCKET” except the “DOC-EXAMPLE-BUCKET/secrets” bucket
    - [ ] C. Access on all objects in the “DOC-EXAMPLE-BUCKET” bucket along with access to all S3 actions for objects in the “DOC-EXAMPLE-BUCKET” bucket that start with “secrets”
    - [ ] D. Access on all objects in the “DOC-EXAMPLE-BUCKET” bucket except on objects that start with “secrets”

    <details>
       <summary>Answer</summary>

       D.

    </details>

48. A developer is creating a mobile app that calls a backend service by using an Amazon API Gateway REST API. For integration testing during the development phase, the developer wants to simulate different backend responses without invoking the backend service. Which solution will meet these requirements with the LEAST operational overhead?
    - [ ] A. Create an AWS Lambda function. Use API Gateway proxy integration to return constant HTTP responses.
    - [ ] B. Create an Amazon EC2 instance that serves the backend REST API by using an AWS CloudFormation template.
    - [ ] C. Customize the API Gateway stage to select a response type based on the request.
    - [ ] D. Use a request mapping template to select the mock integration response.

    <details>
       <summary>Answer</summary>

       D.
      API Gateway provides a feature called "Mock Integration" which allows you to return a specific response without invoking any backend service. By using request mapping templates, you can decide which mock response to return based on the incoming request.

    </details>

49. A developer is using an AWS Lambda function to generate avatars for profile pictures that are uploaded to an Amazon S3 bucket. The Lambda function is automatically invoked for profile pictures that are saved under the /original/ S3 prefix. The developer notices that some pictures cause the Lambda function to time out. The developer wants to implement a fallback mechanism by using another Lambda function that resizes the profile picture. Which solution will meet these requirements with the LEAST development effort?
    - [ ] A. Set the image resize Lambda function as a destination of the avatar generator Lambda function for the events that fail processing.
    - [ ] B. Create an Amazon Simple Queue Service (Amazon SQS) queue. Set the SQS queue as a destination with an on failure condition for the avatar generator Lambda function. Configure the image resize Lambda function to poll from the SQS queue.
    - [ ] C. Create an AWS Step Functions state machine that invokes the avatar generator Lambda function and uses the image resize Lambda function as a fallback. Create an Amazon EventBridge rule that matches events from the S3 bucket to invoke the state machine.
    - [ ] D. Create an Amazon Simple Notification Service (Amazon SNS) topic. Set the SNS topic as a destination with an on failure condition for the avatar generator Lambda function. Subscribe the image resize Lambda function to the SNS topic.

    <details>
       <summary>Answer</summary>

       A:
        Lambda destinations allow you to specify another AWS resource (like another Lambda function, SQS, SNS, etc.) to route the results of a Lambda function (success or failure). This approach allows for a direct connection between the primary Lambda function and the fallback function without the need for extra components or configurations.

    </details>

50. A developer needs to migrate an online retail application to AWS to handle an anticipated increase in traffic. The application currently runs on two servers: one server for the web application and another server for the database. The web server renders webpages and manages session state in memory. The database server hosts a MySQL database that contains order details. When traffic to the application is heavy, the memory usage for the web server approaches 100% and the application slows down considerably. The developer has found that most of the memory increase and performance decrease is related to the load of managing additional user sessions. For the web server migration, the developer will use Amazon EC2 instances with an Auto Scaling group behind an Application Load Balancer. Which additional set of changes should the developer make to the application to improve the application's performance?
    - [ ] A. Use an EC2 instance to host the MySQL database. Store the session data and the application data in the MySQL database.
    - [ ] B. Use Amazon ElastiCache for Memcached to store and manage the session data. Use an Amazon RDS for MySQL DB instance to store the application data.
    - [ ] C. Use Amazon ElastiCache for Memcached to store and manage the session data and the application data.
    - [ ] D. Use the EC2 instance store to manage the session data. Use an Amazon RDS for MySQL DB instance to store the application data.

    <details>
       <summary>Answer</summary>

       B.

    </details>

51. A company is using an AWS Lambda function to process records from an Amazon Kinesis data stream. The company recently observed slow processing of the records. A developer notices that the iterator age metric for the function is increasing and that the Lambda run duration is constantly above normal. Which actions should the developer take to increase the processing speed? (Choose two.)
    - [ ] A. Increase the number of shards of the Kinesis data stream.
    - [ ] B. Decrease the timeout of the Lambda function.
    - [ ] C. Increase the memory that is allocated to the Lambda function.
    - [ ] D. Decrease the number of shards of the Kinesis data stream.
    - [ ] E. Increase the timeout of the Lambda function.

    <details>
       <summary>Answer</summary>

       AC.

    </details>

52. A company needs to harden its container images before the images are in a running state. The company's application uses Amazon Elastic Container Registry (Amazon ECR) as an image registry. Amazon Elastic Kubernetes Service (Amazon EKS) for compute, and an AWS CodePipeline pipeline that orchestrates a continuous integration and continuous delivery (CI/CD) workflow. Dynamic application security testing occurs in the final stage of the pipeline after a new image is deployed to a development namespace in the EKS cluster. A developer needs to place an analysis stage before this deployment to analyze the container image earlier in the CI/CD pipeline. Which solution will meet these requirements with the MOST operational efficiency?
    - [ ] A. Build the container image and run the docker scan command locally. Mitigate any findings before pushing changes to the source code repository. Write a pre-commit hook that enforces the use of this workflow before commit.
    - [ ] B. Create a new CodePipeline stage that occurs after the container image is built. Configure ECR basic image scanning to scan on image push. Use an AWS Lambda function as the action provider. Configure the Lambda function to check the scan results and to fail the pipeline if there are findings.
    - [ ] C. Create a new CodePipeline stage that occurs after source code has been retrieved from its repository. Run a security scanner on the latest revision of the source code. Fail the pipeline if there are findings.
    - [ ] D. Add an action to the deployment stage of the pipeline so that the action occurs before the deployment to the EKS cluster. Configure ECR basic image scanning to scan on image push. Use an AWS Lambda function as the action provider. Configure the Lambda function to check the scan results and to fail the pipeline if there are findings.

    <details>
       <summary>Answer</summary>

       B.

    </details>

53. A developer is testing a new file storage application that uses an Amazon CloudFront distribution to serve content from an Amazon S3 bucket. The distribution accesses the S3 bucket by using an origin access identity (OAI). The S3 bucket's permissions explicitly deny access to all other users. The application prompts users to authenticate on a login page and then uses signed cookies to allow users to access their personal storage directories. The developer has configured the distribution to use its default cache behavior with restricted viewer access and has set the origin to point to the S3 bucket. However, when the developer tries to navigate to the login page, the developer receives a 403 Forbidden error. The developer needs to implement a solution to allow unauthenticated access to the login page. The solution also must keep all private content secure. Which solution will meet these requirements?
    - [ ] A. Add a second cache behavior to the distribution with the same origin as the default cache behavior. Set the path pattern for the second cache behavior to the path of the login page, and make viewer access unrestricted. Keep the default cache behavior’s settings unchanged.
    - [ ] B. Add a second cache behavior to the distribution with the same origin as the default cache behavior. Set the path pattern for the second cache behavior to *, and make viewer access restricted. Change the default cache behavior's path pattern to the path of the login page, and make viewer access unrestricted.
    - [ ] C. Add a second origin as a failover origin to the default cache behavior. Point the failover origin to the S3 bucket. Set the path pattern for the primary origin to * and make viewer access restricted. Set the path pattern for the failover origin to the path of the login page, and make viewer access unrestricted.
    - [ ] D. Add a bucket policy to the S3 bucket to allow read access. Set the resource on the policy to the Amazon Resource Name (ARN) of the login page object in the S3 bucket. Add a CloudFront function to the default cache behavior to redirect unauthorized requests to the login page’s S3 URI.

    <details>
       <summary>Answer</summary>

       A.
       The S3 bucket denies access to all users except the OAI associated with the CloudFront distribution.
       1. Users authenticate through a login page.
       2. After authentication, signed cookies allow access to personal storage directories.
       3. Currently, there's a 403 Forbidden error when trying to access the login page, indicating it's not publicly accessible.
       Given the options:
       - A. This option involves creating a second cache behavior that matches the path of the login page and making viewer access unrestricted. This would mean that when CloudFront gets a request matching the login page's path, it would not require signed cookies, allowing public access to the login page. Meanwhile, the default cache behavior would handle all other paths and require signed cookies. This seems like a potential solution.
       - B. Setting the path pattern of the second cache behavior to * and changing the default cache behavior's path pattern to the login page's path seems counterintuitive and may result in misconfiguration.
       - C. CloudFront doesn't support the concept of a "failover origin" in the manner described in this option.
       - D. The problem with this solution is that direct read access to the login page object in the S3 bucket bypasses CloudFront, which is not recommended as it might expose the S3 URL to the users. Additionally, redirecting unauthorized requests to the S3 URI may expose the S3 URL and cause potential security concerns.

    </details>

54. A developer is using AWS Amplify Hosting to build and deploy an application. The developer is receiving an increased number of bug reports from users. The developer wants to add end-to-end testing to the application to eliminate as many bugs as possible before the bugs reach production. Which solution should the developer implement to meet these requirements?
    - [ ] A. Run the amplify add test command in the Amplify CLI.
    - [ ] B. Create unit tests in the application. Deploy the unit tests by using the amplify push command in the Amplify CLI.
    - [ ] C. Add a test phase to the amplify.yml build settings for the application.
    - [ ] D. Add a test phase to the aws-exports.js file for the application.

    <details>
       <summary>Answer</summary>

       C.

    </details>

55. An ecommerce company is using an AWS Lambda function behind Amazon API Gateway as its application tier. To process orders during checkout, the application calls a POST API from the frontend. The POST API invokes the Lambda function asynchronously. In rare situations, the application has not processed orders. The Lambda application logs show no errors or failures. What should a developer do to solve this problem?
    - [ ] A. Inspect the frontend logs for API failures. Call the POST API manually by using the requests from the log file.
    - [ ] B. Create and inspect the Lambda dead-letter queue. Troubleshoot the failed functions. Reprocess the events.
    - [ ] C. Inspect the Lambda logs in Amazon CloudWatch for possible errors. Fix the errors.
    - [ ] D. Make sure that caching is disabled for the POST API in API Gateway.

    <details>
       <summary>Answer</summary>

       B.
       The POST API invokes the Lambda function asynchronously.
       1. In rare situations, the application has not processed orders.
       2. Lambda application logs show no errors or failures.
       3. Given this, it suggests that the Lambda function might have encountered an error when trying to process the event, but this error hasn't been captured or handled in the logs. When Lambda is invoked asynchronously and it encounters an error that prevents the function from processing the event, AWS Lambda can be set up to send the event to a dead-letter queue (DLQ) for further analysis.
       Let's evaluate the options:
       - A. If the Lambda logs show no errors, and given that the issue is with order processing in the backend, inspecting frontend logs might not provide much insight into the Lambda processing issue.
       - B. A dead-letter queue (DLQ) captures unprocessed events caused by any error when a Lambda function is invoked asynchronously. If a Lambda function is set up with a DLQ, you can determine the cause of an error by inspecting the DLQ. This approach allows for troubleshooting and reprocessing events.
       - C. The problem statement already mentioned that the Lambda application logs show no errors or failures, so revisiting the Lambda logs may not be productive.
       - D. Caching for POST API requests is not typical. POST requests usually entail changing data or state on the server-side, and it's not recommended to cache such requests. However, while this is a best practice, it doesn't directly address the issue described.

    </details>

56. A company is building a web application on AWS. When a customer sends a request, the application will generate reports and then make the reports available to the customer within one hour. Reports should be accessible to the customer for 8 hours. Some reports are larger than 1 MB. Each report is unique to the customer. The application should delete all reports that are older than 2 days. Which solution will meet these requirements with the LEAST operational overhead?
    - [ ] A. Generate the reports and then store the reports as Amazon DynamoDB items that have a specified TTL. Generate a URL that retrieves the reports from DynamoDB. Provide the URL to customers through the web application.
    - [ ] B. Generate the reports and then store the reports in an Amazon S3 bucket that uses server-side encryption. Attach the reports to an Amazon Simple Notification Service (Amazon SNS) message. Subscribe the customer to email notifications from Amazon SNS.
    - [ ] C. Generate the reports and then store the reports in an Amazon S3 bucket that uses server-side encryption. Generate a presigned URL that contains an expiration date Provide the URL to customers through the web application. Add S3 Lifecycle configuration rules to the S3 bucket to delete old reports.
    - [ ] D. Generate the reports and then store the reports in an Amazon RDS database with a date stamp. Generate an URL that retrieves the reports from the RDS database. Provide the URL to customers through the web application. Schedule an hourly AWS Lambda function to delete database records that have expired date stamps.

    <details>
       <summary>Answer</summary>

       C.
       - A: DynamoDB cannot store object larger than 400K
       - B: SNS cannot send email with attachment
       - D: The nature or format of the report is not specified, however RDS doent look like a great place to store large document file. Also generating a url to the reports from the RDS database requires some work while it is a native capabilities in S3

    </details>

57. A company has deployed an application on AWS Elastic Beanstalk. The company has configured the Auto Scaling group that is associated with the Elastic Beanstalk environment to have five Amazon EC2 instances. If the capacity is fewer than four EC2 instances during the deployment, application performance degrades. The company is using the all-at-once deployment policy. What is the MOST cost-effective way to solve the deployment issue?
    - [ ] A. Change the Auto Scaling group to six desired instances.
    - [ ] B. Change the deployment policy to traffic splitting. Specify an evaluation time of 1 hour.
    - [ ] C. Change the deployment policy to rolling with additional batch. Specify a batch size of 1.
    - [ ] D. Change the deployment policy to rolling. Specify a batch size of 2.

    <details>
       <summary>Answer</summary>

       C.
       - A. Changing the Auto Scaling group to have six desired instances might increase the number of running instances permanently, even if they aren't needed all the time, leading to higher costs.
       - B. The traffic splitting deployment policy works by shifting traffic to the new version in increments. Specifying an evaluation time of 1 hour could potentially expose the new version to a significant portion of the traffic before fully determining its stability. It doesn't guarantee the maintenance of a minimum number of healthy instances.
       - C. The rolling with an additional batch deployment policy launches new instances for every batch, ensuring that you always have the required number of instances running, and then replaces the old ones. If we specify a batch size of 1, it means one instance will be added (total becomes 6), deployed, and once successful, one of the older instances will be terminated, bringing the total back to 5. This method ensures that you never go below the required capacity during deployment.
       - D. The rolling deployment policy works by taking instances out of service, updating them, and then returning them to service. If you specify a batch size of 2, it means that 2 instances will be taken out of service for the deployment. Given the scenario, this would reduce the capacity to 3 instances during deployment, which would degrade application performance.

    </details>

58. A developer is incorporating AWS X-Ray into an application that handles personal identifiable information (PII). The application is hosted on Amazon EC2 instances. The application trace messages include encrypted PII and go to Amazon CloudWatch. The developer needs to ensure that no PII goes outside of the EC2 instances. Which solution will meet these requirements?
    - [ ] A. Manually instrument the X-Ray SDK in the application code.
    - [ ] B. Use the X-Ray auto-instrumentation agent.
    - [ ] C. Use Amazon Macie to detect and hide PII. Call the X-Ray API from AWS Lambda.
    - [ ] D. Use AWS Distro for Open Telemetry.

    <details>
       <summary>Answer</summary>

       A.
       By manually instrumenting the X-Ray SDK in the application code, the developer can have full control over which data is included in the trace messages. This way, the developer can ensure that no PII is sent to X-Ray by carefully handling the PII within the application and not including it in the trace messages.

    </details>

59. A developer is migrating some features from a legacy monolithic application to use AWS Lambda functions instead. The application currently stores data in an Amazon Aurora DB cluster that runs in private subnets in a VPC. The AWS account has one VPC deployed. The Lambda functions and the DB cluster are deployed in the same AWS Region in the same AWS account. The developer needs to ensure that the Lambda functions can securely access the DB cluster without crossing the public internet. Which solution will meet these requirements?
    - [ ] A. Configure the DB cluster's public access setting to Yes.
    - [ ] B. Configure an Amazon RDS database proxy for he Lambda functions.
    - [ ] C. Configure a NAT gateway and a security group for the Lambda functions.
    - [ ] D. Configure the VPC, subnets, and a security group for the Lambda functions.

    <details>
       <summary>Answer</summary>

       D.

    </details>

60. A developer is building a new application on AWS. The application uses an AWS Lambda function that retrieves information from an Amazon DynamoDB table. The developer hard coded the DynamoDB table name into the Lambda function code. The table name might change over time. The developer does not want to modify the Lambda code if the table name changes. Which solution will meet these requirements MOST efficiently?

    - [ ] A. Create a Lambda environment variable to store the table name. Use the standard method for the programming language to retrieve the variable.
    - [ ] B. Store the table name in a file. Store the file in the /tmp folder. Use the SDK for the programming language to retrieve the table name.
    - [ ] C. Create a file to store the table name. Zip the file and upload the file to the Lambda layer. Use the SDK for the programming language to retrieve the table name.
    - [ ] D. Create a global variable that is outside the handler in the Lambda function to store the table name.

    <details>
       <summary>Answer</summary>

       A.

    </details>

61. A company has a critical application on AWS. The application exposes an HTTP API by using Amazon API Gateway. The API is integrated with an AWS Lambda function. The application stores data in an Amazon RDS for MySQL DB instance with 2 virtual CPUs (vCPUs) and 64 GB of RAM. Customers have reported that some of the API calls return HTTP 500 Internal Server Error responses. Amazon CloudWatch Logs shows errors for “too many connections.” The errors occur during peak usage times that are unpredictable. The company needs to make the application resilient. The database cannot be down outside of scheduled maintenance hours. Which solution will meet these requirements?
    - [ ] A. Decrease the number of vCPUs for the DB instance. Increase the max_connections setting.
    - [ ] B. Use Amazon RDS Proxy to create a proxy that connects to the DB instance. Update the Lambda function to connect to the proxy.
    - [ ] C. Add a CloudWatch alarm that changes the DB instance class when the number of connections increases to more than 1,000.
    - [ ] D. Add an Amazon EventBridge rule that increases the max_connections setting of the DB instance when CPU utilization is above 75%.

    <details>
       <summary>Answer</summary>

       B.
       Amazon RDS Proxy is designed to improve the application's scalability and resilience by pooling and sharing connections to the database. By using RDS Proxy, the Lambda functions would make connections to the proxy, which would handle and efficiently manage the actual connections to the RDS instance. This would likely alleviate the "too many connections" error during peak times.

    </details>

62. A company has installed smart meters in all its customer locations. The smart meters measure power usage at 1-minute intervals and send the usage readings to a remote endpoint for collection. The company needs to create an endpoint that will receive the smart meter readings and store the readings in a database. The company wants to store the location ID and timestamp information. The company wants to give its customers low-latency access to their current usage and historical usage on demand. The company expects demand to increase significantly. The solution must not impact performance or include downtime while scaling. Which solution will meet these requirements MOST cost-effectively?
    - [ ] A. Store the smart meter readings in an Amazon RDS database. Create an index on the location ID and timestamp columns. Use the columns to filter on the customers' data.
    - [ ] B. Store the smart meter readings in an Amazon DynamoDB table. Create a composite key by using the location ID and timestamp columns. Use the columns to filter on the customers' data.
    - [ ] C. Store the smart meter readings in Amazon ElastiCache for Redis. Create a SortedSet key by using the location ID and timestamp columns. Use the columns to filter on the customers' data.
    - [ ] D. Store the smart meter readings in Amazon S3. Partition the data by using the location ID and timestamp columns. Use Amazon Athena to filter on the customers' data.

    <details>
       <summary>Answer</summary>

       B.

    </details>

63. A company is building a serverless application that uses AWS Lambda functions. The company needs to create a set of test events to test Lambda functions in a development environment. The test events will be created once and then will be used by all the developers in an IAM developer group. The test events must be editable by any of the IAM users in the IAM developer group. Which solution will meet these requirements?
    - [ ] A. Create and store the test events in Amazon S3 as JSON objects. Allow S3 bucket access to all IAM users.
    - [ ] B. Create the test events. Configure the event sharing settings to make the test events shareable.
    - [ ] C. Create and store the test events in Amazon DynamoDB. Allow access to DynamoDB by using IAM roles.
    - [ ] D. Create the test events. Configure the event sharing settings to make the test events private.

    <details>
       <summary>Answer</summary>

       B.
       There is an option in lambda console to share the event with other users.

    </details>

64. A developer is configuring an application's deployment environment in AWS CodePipeline. The application code is stored in a GitHub repository. The developer wants to ensure that the repository package's unit tests run in the new deployment environment. The developer has already set the pipeline's source provider to GitHub and has specified the repository and branch to use in the deployment. Which combination of steps should the developer take next to meet these requirements with the LEAST overhead? (Choose two.)
    - [ ] A. Create an AWS CodeCommit project. Add the repository package's build and test commands to the project's buildspec.
    - [ ] B. Create an AWS CodeBuild project. Add the repository package's build and test commands to the project's buildspec.
    - [ ] C. Create an AWS CodeDeploy project. Add the repository package's build and test commands to the project's buildspec.
    - [ ] D. Add an action to the source stage. Specify the newly created project as the action provider. Specify the build artifact as the action's input artifact.
    - [ ] E. Add a new stage to the pipeline after the source stage. Add an action to the new stage. Specify the newly created project as the action provider. Specify the source artifact as the action's input artifact.

    <details>
       <summary>Answer</summary>

       BE.

    </details>

65. An engineer created an A/B test of a new feature on an Amazon CloudWatch Evidently project. The engineer configured two variations of the feature (Variation A and Variation B) for the test. The engineer wants to work exclusively with Variation A. The engineer needs to make updates so that Variation A is the only variation that appears when the engineer hits the application's endpoint. Which solution will meet this requirement?
    - [ ] A. Add an override to the feature. Set the identifier of the override to the engineer's user ID. Set the variation to Variation A.
    - [ ] B. Add an override to the feature. Set the identifier of the override to Variation A. Set the variation to 100%.
    - [ ] C. Add an experiment to the project. Set the identifier of the experiment to Variation B. Set the variation to 0%.
    - [ ] D. Add an experiment to the project. Set the identifier of the experiment to the AWS account's account ISet the variation to Variation A.

    <details>
       <summary>Answer</summary>

       A.
       (Optional) To specify that certain users always see a certain variation, choose Overrides, Add override. Then, specify a user by entering their user ID, account ID, or some other identifier in Identifier, and specify which variation they should see. This can be useful for members of your own testing team or other internal users when you want to make sure they see a specific variation. The sessions of users who are assigned overrides do not contribute to launch or experiment metrics. You can repeat this for as many as 10 users by choosing Add override again.

    </details>

66. A development team wants to build a continuous integration/continuous delivery (CI/CD) pipeline. The team is using AWS CodePipeline to automate the code build and deployment. The team wants to store the program code to prepare for the CI/CD pipeline. Which AWS service should the team use to store the program code?
    - [ ] A. AWS CodeDeploy
    - [ ] B. AWS CodeArtifact
    - [ ] C. AWS CodeCommit
    - [ ] D. Amazon CodeGuru

    <details>
       <summary>Answer</summary>

       C.

    </details>

67. A developer is working on a serverless application that needs to process any changes to an Amazon DynamoDB table with an AWS Lambda function. How should the developer configure the Lambda function to detect changes to the DynamoDB table?
    - [ ] A. Create an Amazon Kinesis data stream, and attach it to the DynamoDB table. Create a trigger to connect the data stream to the Lambda function.
    - [ ] B. Create an Amazon EventBridge rule to invoke the Lambda function on a regular schedule. Conned to the DynamoDB table from the Lambda function to detect changes.
    - [ ] C. Enable DynamoDB Streams on the table. Create a trigger to connect the DynamoDB stream to the Lambda function.
    - [ ] D. Create an Amazon Kinesis Data Firehose delivery stream, and attach it to the DynamoDB table. Configure the delivery stream destination as the Lambda function.

    <details>
       <summary>Answer</summary>

       C.

    </details>

68. A developer has a legacy application that is hosted on-premises. Other applications hosted on AWS depend on the on-premises application for proper functioning. In case of any application errors, the developer wants to be able to use Amazon CloudWatch to monitor and troubleshoot all applications from one place. How can the developer accomplish this?
    - [ ] A. Install an AWS SDK on the on-premises server to automatically send logs to CloudWatch.
    - [ ] B. Download the CloudWatch agent to the on-premises server. Configure the agent to use IAM user credentials with permissions for CloudWatch.
    - [ ] C. Upload log files from the on-premises server to Amazon S3 and have CloudWatch read the files.
    - [ ] D. Upload log files from the on-premises server to an Amazon EC2 instance and have the instance forward the logs to CloudWatch.

    <details>
       <summary>Answer</summary>

       B.

    </details>

69. An Amazon Kinesis Data Firehose delivery stream is receiving customer data that contains personally identifiable information. A developer needs to remove pattern-based customer identifiers from the data and store the modified data in an Amazon S3 bucket. What should the developer do to meet these requirements?
    - [ ] A. Implement Kinesis Data Firehose data transformation as an AWS Lambda function. Configure the function to remove the customer identifiers. Set an Amazon S3 bucket as the destination of the delivery stream.
    - [ ] B. Launch an Amazon EC2 instance. Set the EC2 instance as the destination of the delivery stream. Run an application on the EC2 instance to remove the customer identifiers. Store the transformed data in an Amazon S3 bucket.
    - [ ] C. Create an Amazon OpenSearch Service instance. Set the OpenSearch Service instance as the destination of the delivery stream. Use search and replace to remove the customer identifiers. Export the data to an Amazon S3 bucket.
    - [ ] D. Create an AWS Step Functions workflow to remove the customer identifiers. As the last step in the workflow, store the transformed data in an Amazon S3 bucket. Set the workflow as the destination of the delivery stream.

    <details>
       <summary>Answer</summary>

       A.

    </details>

70. An application uses Lambda functions to extract metadata from files uploaded to an S3 bucket; the metadata is stored in Amazon DynamoDB. The application starts behaving unexpectedly, and the developer wants to examine the logs of the Lambda function code for errors. Based on this system configuration, where would the developer find the logs?
    - [ ] A. Amazon S3
    - [ ] B. AWS CloudTrail
    - [ ] C. Amazon CloudWatch
    - [ ] D. Amazon DynamoDB

    <details>
       <summary>Answer</summary>

       C.

    </details>

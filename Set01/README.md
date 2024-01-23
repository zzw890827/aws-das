# AWS DAS 01

1. A financial services company needs to aggregate daily stock trade data from the exchanges into a data store. The company requires that data be streamed directly into the data store, but also occasionally allows data to be modified using SQL. The solution should integrate complex, analytic queries running with minimal latency. The solution must provide a business intelligence dashboard that enables viewing of the top contributors to anomalies in stock prices. Which solution meets the company's requirements?
   - [ ] A. Use Amazon Kinesis Data Firehose to stream data to Amazon S3. Use Amazon Athena as a data source for Amazon QuickSight to create a business intelligence dashboard.
   - [ ] B. Use Amazon Kinesis Data Streams to stream data to Amazon Redshift. Use Amazon Redshift as a data source for Amazon QuickSight to create a business intelligence dashboard.
   - [ ] C. Use Amazon Kinesis Data Firehose to stream data to Amazon Redshift. Use Amazon Redshift as a data source for Amazon QuickSight to create a business intelligence dashboard.
   - [ ] D. Use Amazon Kinesis Data Streams to stream data to Amazon S3. Use Amazon Athena as a data source for Amazon QuickSight to create a business intelligence dashboard.
   <details>
      <summary>Answer</summary>

      C.
      - Amazon Kinesis Data Streams: This service is designed for real-time data streaming. It captures and stores data streams, but it doesn't directly integrate with Amazon S3 or Amazon Redshift for data storage. To move data from Kinesis Data Streams to S3 or Redshift, you generally need an additional processing step, such as using AWS Lambda or Amazon Kinesis Data Firehose.
      - Amazon Kinesis Data Firehose: It is designed to capture, transform, and load streaming data directly into AWS data stores like Amazon S3, Amazon Redshift, Amazon Elasticsearch Service, and Splunk. It can be used to deliver streaming data directly to Amazon S3 and from there to Amazon Redshift, often through a buffering and batching process, which makes it more suited for near real-time data processing rather than real-time.
      - A. Amazon Kinesis Data Firehose to Amazon S3, Amazon Athena for querying, Amazon QuickSight for dashboard: This solution is viable for near real-time data streaming to S3, with Athena allowing SQL-like querying and QuickSight providing dashboard capabilities. However, there might be some latency in data availability and query response, especially for complex analytics.
      - B. Amazon Kinesis Data Streams to Amazon Redshift, QuickSight for dashboard: This option would require an additional component (like AWS Lambda) to process and move data from Kinesis Data Streams to Redshift, but it would enable more real-time analysis and querying in Redshift, with QuickSight for dashboards.
      - C. Amazon Kinesis Data Firehose to Amazon Redshift, QuickSight for dashboard: This solution allows for near real-time streaming of data directly into Redshift, which is ideal for complex SQL queries and analytics with minimal latency. QuickSight can then be used for effective data visualization and dashboarding. This option seems to meet all the requirements efficiently.
      - D. Amazon Kinesis Data Streams to Amazon S3, Athena for querying, QuickSight for dashboard: Similar to option A, but requires an additional mechanism to move data from Kinesis Data Streams to S3.

   </details>

2. A financial company hosts a data lake in Amazon S3 and a data warehouse on an Amazon Redshift cluster. The company uses Amazon QuickSight to build dashboards and wants to secure access from its on-premises Active Directory to Amazon QuickSight. How should the data be secured?
   - [ ] A. Use an Active Directory connector and single sign-on (SSO) in a corporate network environment.
   - [ ] B. Use a VPC endpoint to connect to Amazon S3 from Amazon QuickSight and an IAM role to authenticate Amazon Redshift.
   - [ ] C. Establish a secure connection by creating an S3 endpoint to connect Amazon QuickSight and a VPC endpoint to connect to Amazon Redshift.
   - [ ] D. Place Amazon QuickSight and Amazon Redshift in the security group and use an Amazon S3 endpoint to connect Amazon QuickSight to Amazon S3.

   <details>
      <summary>Answer</summary>

      A.
      - A. Using an Active Directory connector with SSO allows users to access Amazon QuickSight using their existing corporate credentials, which simplifies the login process and maintains security.
      - B. This option secures data access but does not address the integration with on-premises Active Directory for user authentication.
      - C. Like option B, it doesn't cover the integration with on-premises Active Directory.
      - D. Tt doesn't specifically address the use of on-premises Active Directory for authentication, and QuickSight doesn't reside within a VPC or security group as it's a managed service.

   </details>

3. A real estate company has a mission-critical application using Apache HBase in Amazon EMR. Amazon EMR is configured with a single master node. The company has over 5 TB of data stored on an Hadoop Distributed File System (HDFS). The company wants a cost-effective solution to make its HBase data highly available. Which architectural pattern meets company's requirements?
   - [ ] A. Use Spot Instances for core and task nodes and a Reserved Instance for the EMR master node. Configure the EMR cluster with multiple master nodes. Schedule automated snapshots using Amazon EventBridge.
   - [ ] B. Store the data on an EMR File System (EMRFS) instead of HDFS. Enable EMRFS consistent view. Create an EMR HBase cluster with multiple master nodes. Point the HBase root directory to an Amazon S3 bucket.
   - [ ] C. Store the data on an EMR File System (EMRFS) instead of HDFS and enable EMRFS consistent view. Run two separate EMR clusters in two different Availability Zones. Point both clusters to the same HBase root directory in the same Amazon S3 bucket.
   - [ ] D. Store the data on an EMR File System (EMRFS) instead of HDFS and enable EMRFS consistent view. Create a primary EMR HBase cluster with multiple master nodes. Create a secondary EMR HBase read-replica cluster in a separate Availability Zone. Point both clusters to the same HBase root directory in the same Amazon S3 bucket.

   <details>
      <summary>Answer</summary>

      B.
      - A. This option doesn't change the fact that data is still stored on HDFS, which is tied to the EMR cluster's lifecycle.
      - B. Storing data on EMR File System (EMRFS) instead of HDFS allows the data to be separated from the cluster lifecycle, as EMRFS uses Amazon S3. EMRFS consistent view ensures data consistency. Multiple master nodes in the EMR cluster improve availability.Storing data in S3 enhances data durability and availability. This option effectively addresses both high availability and durable storage.
      - C. Running two separate EMR clusters in different AZs adds redundancy but might be overkill and cost-ineffective for high availability requirements.
      - D. A read-replica cluster in a separate AZ adds read scalability and improves availability but also adds complexity and cost.

   </details>

4. A software company hosts an application on AWS, and new features are released weekly. As part of the application testing process, a solution must be developed that analyzes logs from each Amazon EC2 instance to ensure that the application is working as expected after each deployment. The collection and analysis solution should be highly available with the ability to display new information with minimal delays. Which method should the company use to collect and analyze the logs?
   - [ ] A. Enable detailed monitoring on Amazon EC2, use Amazon CloudWatch agent to store logs in Amazon S3, and use Amazon Athena for fast, interactive log analytics.
   - [ ] B. Use the Amazon Kinesis Producer Library (KPL) agent on Amazon EC2 to collect and send data to Kinesis Data Streams to further push the data to Amazon Elasticsearch Service and visualize using Amazon QuickSight.
   - [ ] C. Use the Amazon Kinesis Producer Library (KPL) agent on Amazon EC2 to collect and send data to Kinesis Data Firehose to further push the data to Amazon Elasticsearch Service and Kibana.
   - [ ] D. Use Amazon CloudWatch subscriptions to get access to a real-time feed of logs and have the logs delivered to Amazon Kinesis Data Streams to further push the data to Amazon Elasticsearch Service and Kibana.

   <details>
      <summary>Answer</summary>

      C.
      - A. This method may not provide the real-time analysis capabilities, as there could be a delay in logs being available in S3 and then queried by Athena.
      - B. This solution might be more complex to set up and manage.
      - C. It provides a streamlined process for real-time data collection, analysis, and visualization using Kinesis Data Firehose, Amazon Elasticsearch Service, and Kibana. This setup should meet the requirements for real-time log analysis with minimal delay in displaying new information.
      - D. This solution involves multiple services which might increase complexity and cost.

   </details>

5. A data analyst is using AWS Glue to organize, cleanse, validate, and format a 200 GB dataset. The data analyst triggered the job to run with the Standard worker type. After 3 hours, the AWS Glue job status is still RUNNING. Logs from the job run show no error codes. The data analyst wants to improve the job execution time without overprovisioning. Which actions should the data analyst take?
   - [ ] A. Enable job bookmarks in AWS Glue to estimate the number of data processing units (DPUs). Based on the profiled metrics, increase the value of the executor- cores job parameter.
   - [ ] B. Enable job metrics in AWS Glue to estimate the number of data processing units (DPUs). Based on the profiled metrics, increase the value of the maximum capacity job parameter.
   - [ ] C. Enable job metrics in AWS Glue to estimate the number of data processing units (DPUs). Based on the profiled metrics, increase the value of the spark.yarn.executor.memoryOverhead job parameter.
   - [ ] D. Enable job bookmarks in AWS Glue to estimate the number of data processing units (DPUs). Based on the profiled metrics, increase the value of the num- executors job parameter.

   <details>
      <summary>Answer</summary>

      B.
      - A. Job bookmarks can help in efficiently processing only the new or changed data, reducing the total amount of data processed in subsequent runs. However, Job bookmarks are more about efficiently managing data processing rather than speeding up a currently running job.
      - B. Job metrics provide insight into the job's performance and resource utilization, which is essential for optimization. Adjusting the maximum capacity parameter directly affects the number of DPUs allocated, potentially speeding up the job by increasing parallel processing power.
      - C. This approach is only useful if the current bottleneck is related to memory overhead, not overall DPU or CPU capacity.
      - D. Similar to option A, job bookmarks are not directly related to the immediate improvement of the running job’s performance.

   </details>

6. A company has a business unit uploading .csv files to an Amazon S3 bucket. The company's data platform team has set up an AWS Glue crawler to do discovery, and create tables and schemas. An AWS Glue job writes processed data from the created tables to an Amazon Redshift database. The AWS Glue job handles column mapping and creating the Amazon Redshift table appropriately. When the AWS Glue job is rerun for any reason in a day, duplicate records are introduced into the Amazon Redshift table. Which solution will update the Redshift table without duplicates when jobs are rerun?
   - [ ] A. Modify the AWS Glue job to copy the rows into a staging table. Add SQL commands to replace the existing rows in the main table as postactions in the DynamicFrameWriter class.
   - [ ] B. Load the previously inserted data into a MySQL database in the AWS Glue job. Perform an upsert operation in MySQL, and copy the results to the Amazon Redshift table.
   - [ ] C. Use Apache Spark's DataFrame dropDuplicates() API to eliminate duplicates and then write the data to Amazon Redshift.
   - [ ] D. Use the AWS Glue ResolveChoice built-in transform to select the most recent value of the column.

   <details>
      <summary>Answer</summary>

      A.
      - A. It involves copying data into a staging table and then using SQL commands to replace existing rows. This method allows for more control and precision in handling duplicates, particularly if there's a need to update existing records rather than just remove duplicates. However, it's also the most complex in terms of implementation.
      - B. The upsert operation (inserting new records and updating existing ones) effectively prevents duplicates but this approach adds complexity by introducing another database (MySQL) into the workflow and it may not be the most efficient method, especially in terms of time and computational resources.
      - C. Spark's dropDuplicates() is a straightforward way to remove duplicates directly within the AWS Glue job but it may not account for updates to existing records; it only removes exact duplicates.
      - D. It may not effectively address the issue of duplicates unless combined with other methods.

   </details>

7. A streaming application is reading data from Amazon Kinesis Data Streams and immediately writing the data to an Amazon S3 bucket every 10 seconds. The application is reading data from hundreds of shards. The batch interval cannot be changed due to a separate requirement. The data is being accessed by Amazon Athena. Users are seeing degradation in query performance as time progresses. Which action can help improve query performance?
   - [ ] A. Merge the files in Amazon S3 to form larger files.
   - [ ] B. Increase the number of shards in Kinesis Data Streams.
   - [ ] C. Add more memory and CPU capacity to the streaming application.
   - [ ] D. Write the files to multiple S3 buckets.

   <details>
      <summary>Answer</summary>

      A.
      - A. Amazon Athena performance can often degrade due to a large number of small files. Merging these into larger files can significantly improve query performance as Athena is optimized for fewer, larger files.
      - B. Increasing shards can help if the bottleneck is due to the high throughput of data streams but if the issue is related to how the data is stored in S3 and accessed by Athena, adding more shards might not address the query performance degradation.
      - C. This can be beneficial if the application is the bottleneck due to insufficient resources but if the streaming application is performing adequately in its write operations to S3, then adding more resources won’t necessarily improve Athena’s query performance.
      - D. It’s unlikely to significantly impact Athena query performance unless the current bucket has some specific performance issues. Also, it complicates the data architecture.

   </details>

8. A company uses Amazon OpenSearch Service (Amazon Elasticsearch Service) to store and analyze its website clickstream data. The company ingests 1 TB of data daily using Amazon Kinesis Data Firehose and stores one day's worth of data in an Amazon ES cluster. The company has very slow query performance on the Amazon ES index and occasionally sees errors from Kinesis Data Firehose when attempting to write to the index. The Amazon ES cluster has 10 nodes running a single index and 3 dedicated master nodes. Each data node has 1.5 TB of Amazon EBS storage attached and the cluster is configured with 1,000 shards. Occasionally, JVMMemoryPressure errors are found in the cluster logs. Which solution will improve the performance of Amazon ES?
   - [ ] A. Increase the memory of the Amazon ES master nodes.
   - [ ] B. Decrease the number of Amazon ES data nodes.
   - [ ] C. Decrease the number of Amazon ES shards for the index.
   - [ ] D. Increase the number of Amazon ES shards for the index.

   <details>
      <summary>Answer</summary>

      C.
      - A. Increasing the memory could help if the master nodes are the bottleneck. Master nodes are responsible for cluster management tasks but not for query processing or data storage. Since the issue seems to be related to data nodes (given the JVMMemoryPressure errors and slow query performance), increasing memory on master nodes might not resolve the issue.
      - B. This action is not typically a solution for performance issues.
      - C. A high number of shards (1,000 in this case) relative to the data volume (1 TB daily) can lead to inefficiencies and performance issues. Each shard is an overhead, and too many shards can cause problems like increased memory usage and slower query performance. Reducing the number of shards can alleviate JVM memory pressure and improve overall cluster performance.
      - D. Given the existing issue of too many shards, increasing them further would likely worsen performance and memory pressure issues.

   </details>

9. A manufacturing company has been collecting IoT sensor data from devices on its factory floor for a year and is storing the data in Amazon Redshift for daily analysis. A data analyst has determined that, at an expected ingestion rate of about 2 TB per day, the cluster will be undersized in less than 4 months. A long-term solution is needed. The data analyst has indicated that most queries only reference the most recent 13 months of data, yet there are also quarterly reports that need to query all the data generated from the past 7 years. The chief technology officer (CTO) is concerned about the costs, administrative effort, and performance of a long-term solution. Which solution should the data analyst use to meet these requirements?
   - [ ] A. Create a daily job in AWS Glue to UNLOAD records older than 13 months to Amazon S3 and delete those records from Amazon Redshift. Create an external table in Amazon Redshift to point to the S3 location. Use Amazon Redshift Spectrum to join to data that is older than 13 months.
   - [ ] B. Take a snapshot of the Amazon Redshift cluster. Restore the cluster to a new cluster using dense storage nodes with additional storage capacity.
   - [ ] C. Execute a CREATE TABLE AS SELECT (CTAS) statement to move records that are older than 13 months to quarterly partitioned data in Amazon Redshift Spectrum backed by Amazon S3.
   - [ ] D. Unload all the tables in Amazon Redshift to an Amazon S3 bucket using S3 Intelligent-Tiering. Use AWS Glue to crawl the S3 bucket location to create external tables in an AWS Glue Data Catalog. Create an Amazon EMR cluster using Auto Scaling for any daily analytics needs, and use Amazon Athena for the quarterly reports, with both using the same AWS Glue Data Catalog.

   <details>
      <summary>Answer</summary>

      A.
      - A. This approach effectively handles data archiving by moving older data to S3, which is more cost-effective than storing everything in Redshift. Redshift Spectrum allows querying data stored in S3 directly, providing seamless access to archived data.
      - B. It doesn't address the long-term growth of data effectively, as it only provides a temporary increase in storage.
      - C. Requires careful management of the partitioning scheme and ongoing maintenance.
      - Introduces significant complexity in the data architecture and higher administrative effort in managing multiple services (EMR, Athena, Glue, S3).

   </details>

10. An insurance company has raw data in JSON format that is sent without a predefined schedule through an Amazon Kinesis Data Firehose delivery stream to an Amazon S3 bucket. An AWS Glue crawler is scheduled to run every 8 hours to update the schema in the data catalog of the tables stored in the S3 bucket. Data analysts analyze the data using Apache Spark SQL on Amazon EMR set up with AWS Glue Data Catalog as the metastore. Data analysts say that, occasionally, the data they receive is stale. A data engineer needs to provide access to the most up-to-date data. Which solution meets these requirements?
    - [ ] A. Create an external schema based on the AWS Glue Data Catalog on the existing Amazon Redshift cluster to query new data in Amazon S3 with Amazon Redshift Spectrum.
    - [ ] B. Use Amazon CloudWatch Events with the rate (1 hour) expression to execute the AWS Glue crawler every hour.
    - [ ] C. Using the AWS CLI, modify the execution schedule of the AWS Glue crawler from 8 hours to 1 minute.
    - [ ] D. Run the AWS Glue crawler from an AWS Lambda function triggered by an S3:ObjectCreated:* event notification on the S3 bucket.

    <details>
      <summary>Answer</summary>

      D.
      - A. This solution doesn't address the core issue of the Glue crawler's infrequent updates. The data catalog might still be outdated if the crawler is not run soon after new data arrives.
      - B. It might not align perfectly with the arrival of new data, as data is sent without a predefined schedule.
      - C. It may not be practical or efficient, especially if new data doesn't arrive as frequently.
      - D. This approach ensures that the data catalog is updated promptly after new data arrives, thus providing the most current data to the analysts. It aligns the crawler execution closely with the data arrival pattern, which is crucial in this scenario where the data ingestion schedule is not predefined.

     </details>

11. A company that produces network devices has millions of users. Data is collected from the devices on an hourly basis and stored in an Amazon S3 data lake. The company runs analyses on the last 24 hours of data flow logs for abnormality detection and to troubleshoot and resolve user issues. The company also analyzes historical logs dating back 2 years to discover patterns and look for improvement opportunities. The data flow logs contain many metrics, such as date, timestamp, source IP, and target IP. There are about 10 billion events every day. How should this data be stored for optimal performance?
    - [ ] A. In Apache ORC partitioned by date and sorted by source IP
    - [ ] B. In compressed .csv partitioned by date and sorted by source IP
    - [ ] C. In Apache Parquet partitioned by source IP and sorted by date
    - [ ] D. In compressed nested JSON partitioned by source IP and sorted by date
    <details>
       <summary>Answer</summary>

       A.
       - A.  The choice of ORC aligns well with large-scale analytical workloads due to its efficient read and compression capabilities. Partitioning by date is particularly effective for this use case, as it directly supports the company's pattern of analyzing the most recent 24 hours of data and historical logs. While sorting by source IP might not be universally optimal, it can still benefit certain types of queries, especially those focusing on specific source IPs. This approach provides a good balance of query performance, storage efficiency, and alignment with the company's analysis patterns.
       - B. CSV is not an optimal format for read-heavy analytical workloads compared to columnar formats like ORC or Parquet.
       - C. Apache Parquet is another efficient columnar storage format, similar to ORC, and is well-suited for analytical queries but partitioning by source IP might result in a large number of partitions, given the high number of unique IPs, which could lead to partitioning overhead.
       - D. JSON is not as efficient as ORC or Parquet for large-scale analytical queries.

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
       - A. Setting up a trusted connection with an HSM requires both client and server certificates. This step ensures a secure connection between the Redshift cluster and the HSM. The automatic key rotation is a part of complying with the security standards for managing encryption keys.
       - B. This option isn’t feasible because existing Amazon Redshift clusters cannot be modified to add HSM encryption; a new cluster must be created instead.
       - C. Amazon Redshift does not support enabling encryption on an existing cluster. To encrypt the data using HSM, the company must create a new Redshift cluster with HSM encryption enabled and then migrate their data from the unencrypted cluster to the new encrypted one.
       - D. While the AWS CLI can be used for various configurations, enabling HSM encryption on an existing Redshift cluster is not possible; a new cluster needs to be created.
       - E. CDHE is a method for secure key exchange and not directly related to the requirement of encrypting the data at rest using HSM in Amazon Redshift.

    </details>

13. A company is planning to do a proof of concept for a machine learning (ML) project using Amazon SageMaker with a subset of existing on-premises data hosted in the company's 3 TB data warehouse. For part of the project, AWS Direct Connect is established and tested. To prepare the data for ML, data analysts are performing data curation. The data analysts want to perform multiple step, including mapping, dropping null fields, resolving choice, and splitting fields. The company needs the fastest solution to curate the data for this project. Which solution meets these requirements?
    - [ ] A. Ingest data into Amazon S3 using AWS DataSync and use Apache Spark scrips to curate the data in an Amazon EMR cluster. Store the curated data in Amazon S3 for ML processing.
    - [ ] B. Create custom ETL jobs on-premises to curate the data. Use AWS DMS to ingest data into Amazon S3 for ML processing.
    - [ ] C. Ingest data into Amazon S3 using AWS DMS. Use AWS Glue to perform data curation and store the data in Amazon S3 for ML processing.
    - [ ] D. Take a full backup of the data store and ship the backup files using AWS Snowball. Upload Snowball data into Amazon S3 and schedule data curation jobs using AWS Batch to prepare the data for ML.
    <details>
       <summary>Answer</summary>

       C.
       - A. Setting up and optimizing EMR and Spark might require more effort and expertise.
       - B. Performing ETL on-premises adds an extra step and may slow down the process.
       - C. It leverages AWS DMS for efficient data ingestion into S3 and uses AWS Glue, a serverless data integration service, to perform the necessary data curation steps. This approach minimizes the setup and management overhead and benefits from tight integration between AWS services, likely leading to a quicker and smoother data curation process for ML purposes.
       - D. This process is likely slower due to physical shipping.

    </details>

14. A US-based sneaker retail company launched its global website. All the transaction data is stored in Amazon RDS and curated historic transaction data is stored in Amazon Redshift in the us-east-1 Region. The business intelligence (BI) team wants to enhance the user experience by providing a dashboard for sneaker trends. The BI team decides to use Amazon QuickSight to render the website dashboards. During development, a team in Japan provisioned Amazon QuickSight in ap- northeast-1. The team is having difficulty connecting Amazon QuickSight from ap-northeast-1 to Amazon Redshift in us-east-1. Which solution will solve this issue and meet the requirements?
    - [ ] A. In the Amazon Redshift console, choose to configure cross-Region snapshots and set the destination Region as ap-northeast-1. Restore the Amazon Redshift Cluster from the snapshot and connect to Amazon QuickSight launched in ap-northeast-1.
    - [ ] B. Create a VPC endpoint from the Amazon QuickSight VPC to the Amazon Redshift VPC so Amazon QuickSight can access data from Amazon Redshift.
    - [ ] C. Create an Amazon Redshift endpoint connection string with Region information in the string and use this connection string in Amazon QuickSight to connect to Amazon Redshift.
    - [ ] D. Create a new security group for Amazon Redshift in us-east-1 with an inbound rule authorizing access from the appropriate IP address range for the Amazon QuickSight servers in ap-northeast-1.
    <details>
       <summary>Answer</summary>

       D.
       - A. This approach involves significant data duplication and management overhead. It doesn't provide real-time access to the data, as the snapshot is a point-in-time copy.
       - B. Amazon QuickSight does not support VPC endpoints for connecting to Redshift. QuickSight accesses Redshift through public internet or via an Elastic Network Interface (ENI) in the VPC where Redshift resides.
       - C. Amazon QuickSight does not currently support direct cross-region Redshift connectivity simply by specifying the region in the connection string.
       - D. This method allows QuickSight to access Redshift over the public internet, with security group rules ensuring controlled access.

    </details>

15. An airline has .csv-formatted data stored in Amazon S3 with an AWS Glue Data Catalog. Data analysts want to join this data with call center data stored in Amazon Redshift as part of a dally batch process. The Amazon Redshift cluster is already under a heavy load. The solution must be managed, serverless, well- functioning, and minimize the load on the existing Amazon Redshift cluster. The solution should also require minimal effort and development activity. Which solution meets these requirements?
    - [ ] A. Unload the call center data from Amazon Redshift to Amazon S3 using an AWS Lambda function. Perform the join with AWS Glue ETL scripts.
    - [ ] B. Export the call center data from Amazon Redshift using a Python shell in AWS Glue. Perform the join with AWS Glue ETL scripts.
    - [ ] C. Create an external table using Amazon Redshift Spectrum for the call center data and perform the join with Amazon Redshift.
    - [ ] D. Export the call center data from Amazon Redshift to Amazon EMR using Apache Sqoop. Perform the join with Apache Hive.
    <details>
       <summary>Answer</summary>

       C.
       - A. Requires additional effort to set up and maintain the Lambda function and the ETL scripts.
       - B. Similar to Option A, it involves exporting data out of Redshift, which might not be efficient.
       - C. Redshift Spectrum allows querying data directly in S3 without loading it into Redshift, thus minimizing the load on the cluster. This approach is managed and requires minimal additional setup or development. It leverages the existing AWS Glue Data Catalog.
       - D. EMR is not a serverless solution; it requires cluster management and is not as straightforward to set up compared to other options.

    </details>

16. A data analyst is using Amazon QuickSight for data visualization across multiple datasets generated by applications. Each application stores files within a separate Amazon S3 bucket. AWS Glue Data Catalog is used as a central catalog across all application data in Amazon S3. A new application stores its data within a separate S3 bucket. After updating the catalog to include the new application data source, the data analyst created a new Amazon QuickSight data source from an Amazon Athena table, but the import into SPICE failed. How should the data analyst resolve the issue?
    - [ ] A. Edit the permissions for the AWS Glue Data Catalog from within the Amazon QuickSight console.
    - [ ] B. Edit the permissions for the new S3 bucket from within the Amazon QuickSight console.
    - [ ] C. Edit the permissions for the AWS Glue Data Catalog from within the AWS Glue console.
    - [ ] D. Edit the permissions for the new S3 bucket from within the S3 console.

    <details>
       <summary>Answer</summary>

       B.
       - A. While QuickSight needs permissions to access the AWS Glue Data Catalog, if the catalog was already being used for other data sources without issues, it's unlikely that this is the problem.
       - B. This is the most likely solution. QuickSight needs explicit permissions to access each S3 bucket used as a data source. If the new application's data is stored in a separate S3 bucket, QuickSight needs permissions to access this specific bucket.
       - C. Permissions for QuickSight to access the Glue Data Catalog are not managed within the AWS Glue console.
       - D. While S3 bucket permissions are important, QuickSight-specific permissions are typically managed within the QuickSight console, not the S3 console.

    </details>

17. A team of data scientists plans to analyze market trend data for their company's new investment strategy. The trend data comes from five different data sources in large volumes. The team wants to utilize Amazon Kinesis to support their use case. The team uses SQL-like queries to analyze trends and wants to send notifications based on certain significant patterns in the trends. Additionally, the data scientists want to save the data to Amazon S3 for archival and historical re- processing, and use AWS managed services wherever possible. The team wants to implement the lowest-cost solution. Which solution meets these requirements?
    - [ ] A. Publish data to one Kinesis data stream. Deploy a custom application using the Kinesis Client Library (KCL) for analyzing trends, and send notifications using Amazon SNS. Configure Kinesis Data Firehose on the Kinesis data stream to persist data to an S3 bucket.
    - [ ] B. Publish data to one Kinesis data stream. Deploy Kinesis Data Analytic to the stream for analyzing trends, and configure an AWS Lambda function as an output to send notifications using Amazon SNS. Configure Kinesis Data Firehose on the Kinesis data stream to persist data to an S3 bucket.
    - [ ] C. Publish data to two Kinesis data streams. Deploy Kinesis Data Analytics to the first stream for analyzing trends, and configure an AWS Lambda function as an output to send notifications using Amazon SNS. Configure Kinesis Data Firehose on the second Kinesis data stream to persist data to an S3 bucket.
    - [ ] D. Publish data to two Kinesis data streams. Deploy a custom application using the Kinesis Client Library (KCL) to the first stream for analyzing trends, and send notifications using Amazon SNS. Configure Kinesis Data Firehose on the second Kinesis data stream to persist data to an S3 bucket.

    <details>
       <summary>Answer</summary>

       B.
       - A. Developing and maintaining a custom application using KCL adds complexity and potentially higher costs in terms of development and maintenance.
       - B. It utilizes Kinesis Data Analytics, which supports SQL-like queries for analyzing trends, aligning with the data scientists’ skills. AWS Lambda can be configured to handle notifications based on the analysis results, and Amazon SNS can be used for sending those notifications. Finally, Kinesis Data Firehose efficiently handles the persistence of data to an S3 bucket for archival and historical re-processing. This option strikes a balance between meeting the technical requirements and minimizing complexity and cost, utilizing fully managed AWS services.
       - C. Having two Kinesis data streams can add unnecessary complexity and cost without providing significant benefits for the described use case.
       - D. Using a custom KCL application adds complexity and maintenance overhead. Two streams add complexity and potential cost.

    </details>

18. A company currently uses Amazon Athena to query its global datasets. The regional data is stored in Amazon S3 in the us-east-1 and us-west-2 Regions. The data is not encrypted. To simplify the query process and manage it centrally, the company wants to use Athena in us-west-2 to query data from Amazon S3 in both Regions. The solution should be as low-cost as possible. What should the company do to achieve this goal?
    - [ ] A. Use AWS DMS to migrate the AWS Glue Data Catalog from us-east-1 to us-west-2. Run Athena queries in us-west-2.
    - [ ] B. Run the AWS Glue crawler in us-west-2 to catalog datasets in all Regions. Once the data is crawled, run Athena queries in us-west-2.
    - [ ] C. Enable cross-Region replication for the S3 buckets in us-east-1 to replicate data in us-west-2. Once the data is replicated in us-west-2, run the AWS Glue crawler there to update the AWS Glue Data Catalog in us-west-2 and run Athena queries.
    - [ ] D. Update AWS Glue resource policies to provide us-east-1 AWS Glue Data Catalog access to us-west-2. Once the catalog in us-west-2 has access to the catalog in us-east-1, run Athena queries in us-west-2.

    <details>
       <summary>Answer</summary>

       B.
       - A. DMS is not required to migrate data from one region to another. It can even be used to migrate data from an S3 bucket to another bucket in another account, but there are better and cheaper ways to do this (considering the volume of data, of course).
       - B. It is the correct alternative. Glue crawlers can catalog data that is in different regions. It's simple to set up and not expensive.
       - C. Cross-region works for data replication, but it will be duplicated unnecessarily.
       - D. This type of permissions is best suited for LakeFormation and would not help catalog data that is in different regions.

    </details>

19. A large company receives files from external parties in Amazon EC2 throughout the day. At the end of the day, the files are combined into a single file, compressed into a gzip file, and uploaded to Amazon S3. The total size of all the files is close to 100 GB daily. Once the files are uploaded to Amazon S3, an AWS Batch program executes a COPY command to load the files into an Amazon Redshift cluster. Which program modification will accelerate the COPY process?
    - [ ] A. Upload the individual files to Amazon S3 and run the COPY command as soon as the files become available.
    - [ ] B. Split the number of files so they are equal to a multiple of the number of slices in the Amazon Redshift cluster. Gzip and upload the files to Amazon S3. Run the COPY command on the files.
    - [ ] C. Split the number of files so they are equal to a multiple of the number of compute nodes in the Amazon Redshift cluster. Gzip and upload the files to Amazon S3. Run the COPY command on the files.
    - [ ] D. Apply sharding by breaking up the files so the distkey columns with the same values go to the same file. Gzip and upload the sharded files to Amazon S3. Run the COPY command on the files.

    <details>
       <summary>Answer</summary>

       B.
       - A. Doesn't specifically address acceleration of the COPY command itself in terms of performance optimization.
       - B. y splitting the files to align with the number of slices in the Redshift cluster and uploading them to S3, the COPY command can leverage parallel processing more effectively. This alignment ensures that each slice can work on loading data simultaneously, thus speeding up the overall process.
       - C. The number of compute nodes is not as relevant as the number of slices for optimizing the COPY command, as Redshift's performance is more slice-bound than node-bound for data loading.
       - D. While this can improve query performance, it might not necessarily accelerate the COPY process itself, depending on the existing data distribution and query patterns.

    </details>

20. A large ride-sharing company has thousands of drivers globally serving millions of unique customers every day. The company has decided to migrate an existing data mart to Amazon Redshift. The existing schema includes the following tables. ✑ A trips fact table for information on completed rides. ✑ A drivers dimension table for driver profiles. ✑ A customers fact table holding customer profile information. The company analyzes trip details by date and destination to examine profitability by region. The drivers data rarely changes. The customers data frequently changes. What table design provides optimal query performance?
    - [ ] A. Use DISTSTYLE KEY (destination) for the trips table and sort by date. Use DISTSTYLE ALL for the drivers and customers tables.
    - [ ] B. Use DISTSTYLE EVEN for the trips table and sort by date. Use DISTSTYLE ALL for the drivers table. Use DISTSTYLE EVEN for the customers table.
    - [ ] C. Use DISTSTYLE KEY (destination) for the trips table and sort by date. Use DISTSTYLE ALL for the drivers table. Use DISTSTYLE EVEN for the customers table.
    - [ ] D. Use DISTSTYLE EVEN for the drivers table and sort by date. Use DISTSTYLE ALL for both fact tables.
    <details>
       <summary>Answer</summary>

       C.
       - A. DISTSTYLE ALL for the customers table might not be optimal if it's a large table, especially since it frequently changes, leading to potential replication overhead.
       - B. If there are common queries joining the trips table on the destination, DISTSTYLE EVEN might not be as efficient as DISTSTYLE KEY.
       - C. It uses DISTSTYLE KEY for the trips table, aligning with the need to analyze trip details by destination, and sorts it by date, which is another key aspect of the analysis. This option also wisely chooses DISTSTYLE EVEN for the customers table, which is better suited for larger, frequently changing tables, and DISTSTYLE ALL for the drivers table, which is appropriate for smaller, infrequently changing dimension tables. This combination should offer optimal query performance for the described use case and data characteristics.
       - D. DISTSTYLE ALL for large fact tables can lead to unnecessary replication and performance issues, especially for the customers table which frequently changes.

    </details>

21. Three teams of data analysts use Apache Hive on an Amazon EMR cluster with the EMR File System (EMRFS) to query data stored within each teams Amazon S3 bucket. The EMR cluster has Kerberos enabled and is configured to authenticate users from the corporate Active Directory. The data is highly sensitive, so access must be limited to the members of each team. Which steps will satisfy the security requirements?
    - [ ] A. For the EMR cluster Amazon EC2 instances, create a service role that grants no access to Amazon S3. Create three additional IAM roles, each granting access to each team's specific bucket. Add the additional IAM roles to the cluster's EMR role for the EC2 trust policy. Create a security configuration mapping for the additional IAM roles to Active Directory user groups for each team.
    - [ ] B. For the EMR cluster Amazon EC2 instances, create a service role that grants no access to Amazon S3. Create three additional IAM roles, each granting access to each team's specific bucket. Add the service role for the EMR cluster EC2 instances to the trust policies for the additional IAM roles. Create a security configuration mapping for the additional IAM roles to Active Directory user groups for each team.
    - [ ] C. For the EMR cluster Amazon EC2 instances, create a service role that grants full access to Amazon S3. Create three additional IAM roles, each granting access to each team's specific bucket. Add the service role for the EMR cluster EC2 instances to the trust polices for the additional IAM roles. Create a security configuration mapping for the additional IAM roles to Active Directory user groups for each team.
    - [ ] D. For the EMR cluster Amazon EC2 instances, create a service role that grants full access to Amazon S3. Create three additional IAM roles, each granting access to each team's specific bucket. Add the service role for the EMR cluster EC2 instances to the trust polices for the base IAM roles. Create a security configuration mapping for the additional IAM roles to Active Directory user groups for each team.

    <details>
       <summary>Answer</summary>

       B.
       - A. Add IAM roles to EMR's EC2 trust policy: This isn't the usual method. Typically, the EMR service role is added to the trust policy of the IAM roles, not the other way around.
       - B. Add service role for EMR EC2 to the trust policies for the additional IAM roles: This is the correct approach, as the EMR service role should assume these IAM roles.
       - C, D: Add service role for EMR EC2 to the trust policies for the additional IAM roles: This is the correct approach, as the EMR service role should assume these IAM roles.

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
       - AWS Glue Data Catalog (Option A): This serves as a centralized metadata repository for all your data assets, regardless of where they are located. It supports metadata management and federation for access control, which is a key requirement. It is also compatible with many data processing tools like Apache Spark and Athena.
       - Amazon EMR with Apache Spark for ETL (Option B): While EMR with Spark provides powerful processing capabilities for ETL with PySpark and Scala, as you correctly pointed out, it does come with more operational overhead compared to fully managed services.
       - AWS Glue for Scala-based ETL (Option C): AWS Glue is a fully managed ETL service that can handle Scala scripts. However, it might be more limited in operational flexibility compared to EMR with Apache Spark, especially if there's a need for more customized or complex ETL workflows.
       - Amazon EMR with Apache Hive for JDBC clients (Option D): EMR with Apache Hive can provide JDBC support for legacy clients. Hive on EMR can serve as an effective solution for enabling JDBC connectivity to data stored in S3.
       - Amazon Athena for querying data in Amazon S3 using JDBC drivers (Option E): Athena allows SQL querying of data in S3 and supports JDBC connections. It is serverless, so operational management is minimal, and it can be integrated with the AWS Glue Data Catalog.
       - Amazon EMR with Apache Hive, using an Amazon RDS with MySQL-compatible backed metastore (Option F): This setup would provide an external metastore for Hive on EMR, which can offer advantages in some scenarios but may add additional operational complexity.

    </details>

23. A company wants to optimize the cost of its data and analytics platform. The company is ingesting a number of .csv and JSON files in Amazon S3 from various data sources. Incoming data is expected to be 50 GB each day. The company is using Amazon Athena to query the raw data in Amazon S3 directly. Most queries aggregate data from the past 12 months, and data that is older than 5 years is infrequently queried. The typical query scans about 500 MB of data and is expected to return results in less than 1 minute. The raw data must be retained indefinitely for compliance requirements. Which solution meets the company's requirements?
    - [ ] A. Use an AWS Glue ETL job to compress, partition, and convert the data into a columnar data format. Use Athena to query the processed dataset. Configure a lifecycle policy to move the processed data into the Amazon S3 Standard-Infrequent Access (S3 Standard-IA) storage class 5 years after object creation. Configure a second lifecycle policy to move the raw data into Amazon S3 Glacier for long-term archival 7 days after object creation.
    - [ ] B. Use an AWS Glue ETL job to partition and convert the data into a row-based data format. Use Athena to query the processed dataset. Configure a lifecycle policy to move the data into the Amazon S3 Standard-Infrequent Access (S3 Standard-IA) storage class 5 years after object creation. Configure a second lifecycle policy to move the raw data into Amazon S3 Glacier for long-term archival 7 days after object creation.
    - [ ] C. Use an AWS Glue ETL job to compress, partition, and convert the data into a columnar data format. Use Athena to query the processed dataset. Configure a lifecycle policy to move the processed data into the Amazon S3 Standard-Infrequent Access (S3 Standard-IA) storage class 5 years after the object was last accessed. Configure a second lifecycle policy to move the raw data into Amazon S3 Glacier for long-term archival 7 days after the last date the object was accessed.
    - [ ] D. Use an AWS Glue ETL job to partition and convert the data into a row-based data format. Use Athena to query the processed dataset. Configure a lifecycle policy to move the data into the Amazon S3 Standard-Infrequent Access (S3 Standard-IA) storage class 5 years after the object was last accessed. Configure a second lifecycle policy to move the raw data into Amazon S3 Glacier for long-term archival 7 days after the last date the object was accessed.

    <details>
       <summary>Answer</summary>

       A.
       - A. Option A is the most suitable solution. It combines the benefits of compression, partitioning, and converting to a columnar data format, which are all best practices for optimizing Athena query performance and cost. The defined lifecycle policies effectively balance the need for data availability and cost optimization, with raw data moved to Glacier for long-term, cost-effective storage, and processed data moved to S3 Standard-IA after it becomes infrequently accessed. This approach should meet the requirements for query performance, data retention, and cost optimization.
       - B. Partitioning improves query efficiency but using a row-based format may not be as cost-effective as a columnar format for Athena queries.
       - C, D. The lifecycle policy based on last access may keep data in a higher-cost storage class longer than necessary, especially for data that is not accessed frequently but not old enough to be moved to S3-IA.

    </details>

24. A regional energy company collects voltage data from sensors attached to buildings. To address any known dangerous conditions, the company wants to be alerted when a sequence of two voltage drops is detected within 10 minutes of a voltage spike at the same building. It is important to ensure that all messages are delivered as quickly as possible. The system must be fully managed and highly available. The company also needs a solution that will automatically scale up as it covers additional cites with this monitoring feature. The alerting system is subscribed to an Amazon SNS topic for remediation. Which solution meets these requirements?
    - [ ] A. Create an Amazon Managed Streaming for Kafka cluster to ingest the data, and use an Apache Spark Streaming with Apache Kafka consumer API in an automatically scaled Amazon EMR cluster to process the incoming data. Use the Spark Streaming application to detect the known event sequence and send the SNS message.
    - [ ] B. Create a REST-based web service using Amazon API Gateway in front of an AWS Lambda function. Create an Amazon RDS for PostgreSQL database with sufficient Provisioned IOPS (PIOPS). In the Lambda function, store incoming events in the RDS database and query the latest data to detect the known event sequence and send the SNS message.
    - [ ] C. Create an Amazon Kinesis Data Firehose delivery stream to capture the incoming sensor data. Use an AWS Lambda transformation function to detect the known event sequence and send the SNS message.
    - [ ] D. Create an Amazon Kinesis data stream to capture the incoming sensor data and create another stream for alert messages. Set up AWS Application Auto Scaling on both. Create a Kinesis Data Analytics for Java application to detect the known event sequence, and add a message to the message stream. Configure an AWS Lambda function to poll the message stream and publish to the SNS topic.

    <details>
       <summary>Answer</summary>

       D.
       - A. EMR with Spark Streaming for Processing: Provides robust stream processing capabilities. However, managing an EMR cluster requires more operational overhead, and scaling may not be as immediate as other serverless options.
       - B. RDS for Data Storage: While RDS is a managed service, it might introduce latency and complexity in the solution, especially when dealing with high-velocity real-time data. Managing the scaling and IOPS for RDS can also add overhead.
       - C. Lambda for Event Detection: Can be used for real-time processing and is serverless, but integrating complex event detection logic within the constraints of Lambda might be challenging, especially for sequence detection within a timeframe.
       - D. t leverages Amazon Kinesis Data Streams for real-time data ingestion and Kinesis Data Analytics for processing and pattern detection, which is crucial for identifying the sequence of voltage changes. AWS Lambda can then be used to send alerts to the SNS topic. This solution is fully managed, highly available, and can automatically scale, aligning well with the company's needs for real-time alerting in a growing network of cities.

    </details>

25. An ecommerce company stores customer purchase data in Amazon RDS. The company wants a solution to store and analyze historical data. The most recent 6 months of data will be queried frequently for analytics workloads. This data is several terabytes large. Once a month, historical data for the last 5 years must be accessible and will be joined with the more recent data. The company wants to optimize performance and cost. Which storage solution will meet these requirements?
    - [ ] A. Create a read replica of the RDS database to store the most recent 6 months of data. Copy the historical data into Amazon S3. Create an AWS Glue Data Catalog of the data in Amazon S3 and Amazon RDS. Run historical queries using Amazon Athena.
    - [ ] B. Use an ETL tool to incrementally load the most recent 6 months of data into an Amazon Redshift cluster. Run more frequent queries against this cluster. Create a read replica of the RDS database to run queries on the historical data.
    - [ ] C. Incrementally copy data from Amazon RDS to Amazon S3. Create an AWS Glue Data Catalog of the data in Amazon S3. Use Amazon Athena to query the data.
    - [ ] D. Incrementally copy data from Amazon RDS to Amazon S3. Load and store the most recent 6 months of data in Amazon Redshift. Configure an Amazon Redshift Spectrum table to connect to all historical data.

    <details>
       <summary>Answer</summary>

       D.
       - A. Read Replica for Recent Data: Creating a read replica of the RDS database for the most recent 6 months of data may not be the most efficient solution, as RDS is generally used for transactional workloads rather than analytics.
       - B. Read Replica for Historical Data: As with Option A, using a read replica for historical data may not be optimal for analytics. Additionally, joining data across Redshift and RDS can be complex and inefficient.
       - C. AWS Glue Data Catalog and Athena: Using Athena for querying is a good choice for analytics. However, this option does not specify how the most recent data (which is queried more frequently) is managed differently for performance optimization.
       - D. Incremental Copy to S3 with Redshift for Recent Data: Storing historical data in S3 and keeping the recent 6 months in Redshift is an effective approach. Redshift offers excellent performance for frequent queries on the recent data. Redshift Spectrum for Historical Data: Using Redshift Spectrum to query historical data in S3 directly from Redshift is efficient and allows for easy joining with the recent data stored in Redshift.

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
       - A. This approach focuses on data storage in S3. While creating separate buckets and applying specific bucket policies can control access to the data, it doesn't directly address the separation of query execution and history in Athena.
       - B. Athena workgroups are used to separate query execution and control cost. By creating a workgroup for each use case, you can segregate query execution and history. Applying tags and using IAM policies based on these tags can enforce appropriate permissions. This approach aligns well with the requirement to separate query execution and history based on different use cases within the same AWS account.
       - C. While creating different IAM roles with specific permissions can provide access control, it doesn't inherently segregate query execution and history in Athena. IAM roles are more about granting users or services the necessary permissions to perform actions in Athena, rather than separating the query environment.
       - D. AWS Glue Data Catalog resource policies can control access to metadata for tables and databases. However, this approach primarily focuses on access to the metadata rather than the segregation of Athena query execution and history.

    </details>

28. A company wants to use an automatic machine learning (ML) Random Cut Forest (RCF) algorithm to visualize complex real-world scenarios, such as detecting seasonality and trends, excluding outers, and imputing missing values. The team working on this project is non-technical and is looking for an out-of-the-box solution that will require the LEAST amount of management overhead. Which solution will meet these requirements?
    - [ ] A. Use an AWS Glue ML transform to create a forecast and then use Amazon QuickSight to visualize the data.
    - [ ] B. Use Amazon QuickSight to visualize the data and then use ML-powered forecasting to forecast the key business metrics.
    - [ ] C. Use a pre-build ML AMI from the AWS Marketplace to create forecasts and then use Amazon QuickSight to visualize the data.
    - [ ] D. Use calculated fields to create a new forecast and then use Amazon QuickSight to visualize the data.

    <details>
       <summary>Answer</summary>

       B.
       - A. AWS Glue ML Transform can be used for ML tasks, but it's more focused on ETL transformations rather than specific ML algorithms like Random Cut Forest (RCF). Amazon QuickSight is excellent for visualization, but this combination may require some technical oversight for setting up and managing the ML transforms in Glue.
       - B. Using Amazon QuickSight for visualization and leveraging its ML-powered forecasting capabilities, seems to be the best fit. It offers an out-of-the-box, user-friendly solution with minimal management overhead, ideal for a non-technical team. QuickSight's built-in ML features can handle tasks like forecasting and trend detection without the need for deep technical expertise in machine learning or data science.
       - C. This approach requires managing an EC2 instance and the ML model, which could be complex and time-consuming for a non-technical team.
       - D. This option is more suited for simple analyses and may not fully leverage ML capabilities like RCF for complex tasks such as seasonality detection or outlier exclusion.

    </details>

29. A retail company's data analytics team recently created multiple product sales analysis dashboards for the average selling price per product using Amazon QuickSight. The dashboards were created from .csv files uploaded to Amazon S3. The team is now planning to share the dashboards with the respective external product owners by creating individual users in Amazon QuickSight. For compliance and governance reasons, restricting access is a key requirement. The product owners should view only their respective product analysis in the dashboard reports. Which approach should the data analytics team take to allow product owners to view only their products in the dashboard?
    - [ ] A. Separate the data by product and use S3 bucket policies for authorization.
    - [ ] B. Separate the data by product and use IAM policies for authorization.
    - [ ] C. Create a manifest file with row-level security.
    - [ ] D. Create dataset rules with row-level security.

    <details>
       <summary>Answer</summary>

       D.
       - A. This approach involves segregating the data into different S3 buckets or prefixes based on the product. While S3 bucket policies can control access to the data at the S3 level, they do not directly control what data is visible within a QuickSight dashboard.
       - B. Similar to option A, this involves separating the data by product. IAM policies can control access to AWS resources, but like S3 bucket policies, they do not provide a method to control data visibility within QuickSight dashboards.
       - C. Row-level security in QuickSight allows you to control access to data at the row level within a dataset. However, QuickSight’s row-level security is not typically implemented via a manifest file. Manifest files in QuickSight are generally used for defining data sets, especially when importing data from S3.
       - D. This option involves applying row-level security (RLS) directly to datasets in QuickSight. RLS enables the data analytics team to specify which rows of data a user or group of users can access within a dataset. By setting up dataset rules, the team can ensure that each product owner only sees the data relevant to their products.

    </details>

30. A company has developed an Apache Hive script to batch process data stared in Amazon S3. The script needs to run once every day and store the output in Amazon S3. The company tested the script, and it completes within 30 minutes on a small local three-node cluster. Which solution is the MOST cost-effective for scheduling and executing the script?
    - [ ] A. Create an AWS Lambda function to spin up an Amazon EMR cluster with a Hive execution step. Set KeepJobFlowAliveWhenNoSteps to false and disable the termination protection flag. Use Amazon CloudWatch Events to schedule the Lambda function to run daily.
    - [ ] B. Use the AWS Management Console to spin up an Amazon EMR cluster with Python Hue. Hive, and Apache Oozie. Set the termination protection flag to true and use Spot Instances for the core nodes of the cluster. Configure an Oozie workflow in the cluster to invoke the Hive script daily.
    - [ ] C. Create an AWS Glue job with the Hive script to perform the batch operation. Configure the job to run once a day using a time-based schedule.
    - [ ] D. Use AWS Lambda layers and load the Hive runtime to AWS Lambda and copy the Hive script. Schedule the Lambda function to run daily by creating a workflow using AWS Step Functions.

    <details>
       <summary>Answer</summary>

       A.
       - A. This option uses AWS Lambda to create an EMR cluster, execute the Hive script, and then automatically terminate the cluster. By setting KeepJobFlowAliveWhenNoSteps to false, the cluster will shut down once the script completes, ensuring that you only pay for the cluster while it's active. The use of Lambda and CloudWatch Events for scheduling provides a high degree of control over when the job runs and allows for the cluster to be fully terminated between runs, which can be more cost-effective for daily batch jobs.
       - B. While the use of Spot Instances can be cost-effective, leaving the cluster running continuously (due to the termination protection flag) could lead to higher costs, especially if the cluster is underutilized outside the execution time of the daily job.
       - C.  While AWS Glue is a fully managed ETL service that can be highly cost-effective for certain use cases, it does not operate on a bring-up-and-tear-down model like an Amazon EMR cluster. In Glue, you define jobs and triggers, and the underlying resources are managed by AWS. However, you don't have the same level of control over starting and stopping the underlying infrastructure as you do with EMR. This can impact cost, particularly if you need to run jobs infrequently and prefer not to have resources allocated when they are not in use.
       - D. As previously mentioned, this option faces challenges with the execution time limits of AWS Lambda and may not be feasible for a 30-minute Hive script.

    </details>

31. A company wants to improve the data load time of a sales data dashboard. Data has been collected as .csv files and stored within an Amazon S3 bucket that is partitioned by date. The data is then loaded to an Amazon Redshift data warehouse for frequent analysis. The data volume is up to 500 GB per day. Which solution will improve the data loading performance?
    - [ ] A. Compress .csv files and use an INSERT statement to ingest data into Amazon Redshift.
    - [ ] B. Split large .csv files, then use a COPY command to load data into Amazon Redshift.
    - [ ] C. Use Amazon Kinesis Data Firehose to ingest data into Amazon Redshift.
    - [ ] D. Load the .csv files in an unsorted key order and vacuum the table in Amazon Redshift.

    <details>
       <summary>Answer</summary>

       B.
       - A. Using INSERT statements to ingest large amounts of data into Amazon Redshift is not efficient. INSERT is suitable for loading small amounts of data, but for large volumes, it's slow and resource-intensive.
       - B. Splitting large .csv files and then using the COPY command to load data into Amazon Redshift, is the most effective solution for improving data loading performance. This approach leverages Redshift's optimized data loading capabilities and can handle the large daily data volume efficiently.
       - C. It's an efficient way to ingest data, especially if the data is generated continuously or in real-time. However, for batch loading of .csv files stored in S3, it might not be the most straightforward solution compared to directly using the COPY command.
       - D. Loading data in an unsorted order can initially be fast, but it may lead to suboptimal query performance due to data being unorganized.

    </details>

32. A company has a data warehouse in Amazon Redshift that is approximately 500 TB in size. New data is imported every few hours and read-only queries are run throughout the day and evening. There is a particularly heavy load with no writes for several hours each morning on business days. During those hours, some queries are queued and take a long time to execute. The company needs to optimize query execution and avoid any downtime. What is the MOST cost-effective solution?
    - [ ] A. Enable concurrency scaling in the workload management (WLM) queue.
    - [ ] B. Add more nodes using the AWS Management Console during peak hours. Set the distribution style to ALL.
    - [ ] C. Use elastic resize to quickly add nodes during peak times. Remove the nodes when they are not needed.
    - [ ] D. Use a snapshot, restore, and resize operation. Switch to the new target cluster.

    <details>
       <summary>Answer</summary>

       A.
       - A. Concurrency scaling in Amazon Redshift automatically adds additional cluster capacity to handle increases in concurrent read-only queries. It's a cost-effective solution as you get an hour of concurrency scaling cluster time for free each day per main cluster. You're only charged for the concurrency scaling cluster time if it exceeds this amount. This solution is ideal for handling bursts in query activity without the need for manual intervention or permanent resizing of the cluster.
       - B. Manually adding more nodes can increase query processing capacity, but it's less flexible and more time-consuming than automatic scaling solutions. Setting the distribution style to ALL can be beneficial for small reference tables but may not be suitable for all types of queries or tables, especially in a large data warehouse. This approach also requires manual intervention and can be less cost-effective as it involves maintaining a larger cluster size than necessary during non-peak hours.
       - C. While this is a viable solution, it requires manual intervention to scale up and down, and you pay for the additional nodes as long as they are part of the cluster.
       - D. It's a more disruptive and complex process compared to other options, and not necessarily more cost-effective. It could cause downtime or data synchronization issues and is generally not recommended for routine scaling purposes.

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
       - A. While you can specify settings to restrict public internet access, the effectiveness of this solution depends on analysts consistently using the correct security configuration when they launch their clusters.
       - B. Manually checking the security group settings for each EMR cluster to ensure they don't allow public internet access (0.0.0.0/0 for IPv4, ::/0 for IPv6) is a way to ensure compliance. However, this approach is reactive and labor-intensive, requiring ongoing monitoring and doesn't prevent the creation of non-compliant clusters in the first place.
       - C. Enabling the block public access setting at the account level is a proactive and comprehensive way to ensure that no EMR cluster in the account can be accessed from the public internet. This approach requires minimal effort once set up and applies to all current and future EMR clusters within the account, ensuring compliance without relying on individual users' actions.
       - D. AWS WAF (Web Application Firewall) is primarily designed to protect web applications from common web exploits. While it could theoretically be configured to block public access to EMR clusters, it's not the most straightforward or intended tool for this specific use case.

    </details>

35. A company's marketing team has asked for help in identifying a high performing long-term storage service for their data based on the following requirements: ✑ The data size is approximately 32 TB uncompressed. ✑ There is a low volume of single-row inserts each day. ✑ There is a high volume of aggregation queries each day. ✑ Multiple complex joins are performed. ✑ The queries typically involve a small subset of the columns in a table. Which storage service will provide the MOST performant solution?
    - [ ] A. Amazon Aurora MySQL
    - [ ] B. Amazon Redshift
    - [ ] C. Amazon Neptune
    - [ ] D. Amazon Elasticsearch

    <details>
       <summary>Answer</summary>

       B.
       - A. Aurora can handle complex joins and aggregation queries, it may not be optimized for scenarios with a high volume of such operations, especially on large datasets.
       - B. Amazon Redshift, is the most suitable and performant storage service for the specified requirements. Redshift is specifically designed for data warehousing and analytics workloads, making it ideal for handling large volumes of data with a high frequency of complex joins and aggregation queries. Its columnar storage and MPP architecture are particularly well-suited for querying large datasets and performing operations on a subset of columns efficiently.
       - C. While it excels in scenarios where data is highly interconnected (like social networking, fraud detection, etc.), it is not designed for general-purpose data warehousing tasks like the ones described in your requirements.
       - D. While Elasticsearch can handle aggregation queries, it is not primarily designed for data warehousing use cases involving complex joins and typical OLAP operations.

    </details>

36. A financial company uses Amazon S3 as its data lake and has set up a data warehouse using a multi-node Amazon Redshift cluster. The data files in the data lake are organized in folders based on the data source of each data file. All the data files are loaded to one table in the Amazon Redshift cluster using a separate COPY command for each data file location. With this approach, loading all the data files into Amazon Redshift takes a long time to complete. Users want a faster solution with little or no increase in cost while maintaining the segregation of the data files in the S3 data lake. Which solution meets these requirements?
    - [ ] A. Use Amazon EMR to copy all the data files into one folder and issue a COPY command to load the data into Amazon Redshift.
    - [ ] B. Load all the data files in parallel to Amazon Aurora, and run an AWS Glue job to load the data into Amazon Redshift.
    - [ ] C. Use an AWS Glue job to copy all the data files into one folder and issue a COPY command to load the data into Amazon Redshift.
    - [ ] D. Create a manifest file that contains the data file locations and issue a COPY command to load the data into Amazon Redshift.

    <details>
       <summary>Answer</summary>

       D.
       - A. The process of copying data to a single folder might be time-consuming and doesn't leverage Redshift's ability to load data in parallel from multiple locations.
       - B. Introduces significant complexity and additional cost by using Aurora and AWS Glue.
       - C. Similar to option A, this adds complexity and may not be necessary.
       - D. Enables parallel loading of data files from multiple S3 locations, which can significantly speed up the loading process. Does not require moving or altering the data files in S3, maintaining their segregation. Does not add significant cost, as it uses Redshift's built-in capabilities.

    </details>

37. A technology company is creating a dashboard that will visualize and analyze time-sensitive data. The data will come in through Amazon Kinesis Data Firehose with the butter interval set to 60 seconds. The dashboard must support near-real-time data. Which visualization solution will meet these requirements?
    - [ ] A. Select Amazon Elasticsearch Service (Amazon ES) as the endpoint for Kinesis Data Firehose. Set up a Kibana dashboard using the data in Amazon ES with the desired analyses and visualizations.
    - [ ] B. Select Amazon S3 as the endpoint for Kinesis Data Firehose. Read data into an Amazon SageMaker Jupyter notebook and carry out the desired analyses and visualizations.
    - [ ] C. Select Amazon Redshift as the endpoint for Kinesis Data Firehose. Connect Amazon QuickSight with SPICE to Amazon Redshift to create the desired analyses and visualizations.
    - [ ] D. Select Amazon S3 as the endpoint for Kinesis Data Firehose. Use AWS Glue to catalog the data and Amazon Athena to query it. Connect Amazon QuickSight with SPICE to Athena to create the desired analyses and visualizations.

    <details>
       <summary>Answer</summary>

       A.
       - A. Amazon ES is well-suited for real-time data analysis and can handle streaming data efficiently. Kibana offers powerful visualization capabilities and can work with near-real-time data.
       - B. This setup might not support near-real-time analysis since it involves manual steps in SageMaker Jupyter notebooks.
       - C. There might be a delay in data availability due to the data warehouse architecture, potentially affecting the near-real-time requirement.
       - D. The process of data cataloging, querying with Athena, and then visualizing might introduce delays, potentially impacting the near-real-time requirement.

    </details>

38. A financial company uses Apache Hive on Amazon EMR for ad-hoc queries. Users are complaining of sluggish performance. A data analyst notes the following: ✑ Approximately 90% of queries are submitted 1 hour after the market opens. Hadoop Distributed File System (HDFS) utilization never exceeds 10%. Which solution would help address the performance issues?
    - [ ] A. Create instance fleet configurations for core and task nodes. Create an automatic scaling policy to scale out the instance groups based on the Amazon CloudWatch CapacityRemainingGB metric. Create an automatic scaling policy to scale in the instance fleet based on the CloudWatch CapacityRemainingGB metric.
    - [ ] B. Create instance fleet configurations for core and task nodes. Create an automatic scaling policy to scale out the instance groups based on the Amazon CloudWatch YARNMemoryAvailablePercentage metric. Create an automatic scaling policy to scale in the instance fleet based on the CloudWatch YARNMemoryAvailablePercentage metric.
    - [ ] C. Create instance group configurations for core and task nodes. Create an automatic scaling policy to scale out the instance groups based on the Amazon CloudWatch CapacityRemainingGB metric. Create an automatic scaling policy to scale in the instance groups based on the CloudWatch CapacityRemainingGB metric.
    - [ ] D. Create instance group configurations for core and task nodes. Create an automatic scaling policy to scale out the instance groups based on the Amazon CloudWatch YARNMemoryAvailablePercentage metric. Create an automatic scaling policy to scale in the instance groups based on the CloudWatch YARNMemoryAvailablePercentage metric.

    <details>
       <summary>Answer</summary>

       D.
       - A. Since HDFS utilization is already low (never exceeds 10%), scaling based on CapacityRemainingGB might not be responsive to the actual performance bottleneck, which is more likely related to compute capacity rather than HDFS storage.
       - B. Same as Option A regarding instance fleets.
       - C. Similar to Option A, scaling based on CapacityRemainingGB might not effectively address the performance issue if the bottleneck is related to processing power rather than storage capacity.
       - D. This approach focuses on scaling the cluster based on memory availability, which is a critical resource for query processing and is likely to have a more direct impact on improving query performance during peak times.

    </details>

39. A media company has been performing analytics on log data generated by its applications. There has been a recent increase in the number of concurrent analytics jobs running, and the overall performance of existing jobs is decreasing as the number of new jobs is increasing. The partitioned data is stored in Amazon S3 One Zone-Infrequent Access (S3 One Zone-IA) and the analytic processing is performed on Amazon EMR clusters using the EMR File System (EMRFS) with consistent view enabled. A data analyst has determined that it is taking longer for the EMR task nodes to list objects in Amazon S3. Which action would MOST likely increase the performance of accessing log data in Amazon S3?
    - [ ] A. Use a hash function to create a random string and add that to the beginning of the object prefixes when storing the log data in Amazon S3.
    - [ ] B. Use a lifecycle policy to change the S3 storage class to S3 Standard for the log data.
    - [ ] C. Increase the read capacity units (RCUs) for the shared Amazon DynamoDB table.
    - [ ] D. Redeploy the EMR clusters that are running slowly to a different Availability Zone.

    <details>
       <summary>Answer</summary>

       C.
       - A. It requires changing the way data is stored, which might not be feasible for existing data.
       - B. The performance issue described seems more related to listing S3 objects rather than the storage class's performance characteristics.
       - C. EMRFS with consistent view uses DynamoDB to track S3 objects. Increasing RCUs can improve the performance of read operations, which includes listing S3 objects.
       - D. Changing the Availability Zone is unlikely to affect the performance of listing objects in S3.

    </details>

40. A company has developed several AWS Glue jobs to validate and transform its data from Amazon S3 and load it into Amazon RDS for MySQL in batches once every day. The ETL jobs read the S3 data using a DynamicFrame. Currently, the ETL developers are experiencing challenges in processing only the incremental data on every run, as the AWS Glue job processes all the S3 input data on each run. Which approach would allow the developers to solve the issue with minimal coding effort?
    - [ ] A. Have the ETL jobs read the data from Amazon S3 using a DataFrame.
    - [ ] B. Enable job bookmarks on the AWS Glue jobs.
    - [ ] C. Create custom logic on the ETL jobs to track the processed S3 objects.
    - [ ] D. Have the ETL jobs delete the processed objects or data from Amazon S3 after each run.

    <details>
       <summary>Answer</summary>

       B.
       - A. Simply changing from DynamicFrame to DataFrame won't inherently solve the issue of processing incremental data.
       - B. This approach specifically addresses the challenge of processing only incremental data without requiring additional coding. Job bookmarks provide a built-in mechanism to keep track of which data has already been processed, thus ensuring that each subsequent job run only processes new or changed data. This option is not only efficient but also aligns well with the requirement of minimal coding effort.
       - C. Requires significant coding effort and maintenance.
       - D. Deleting data can be risky and might not be desirable or feasible in many scenarios.

    </details>

41. A mortgage company has a microservice for accepting payments. This microservice uses the Amazon DynamoDB encryption client with AWS KMS managed keys to encrypt the sensitive data before writing the data to DynamoDB. The finance team should be able to load this data into Amazon Redshift and aggregate the values within the sensitive fields. The Amazon Redshift cluster is shared with other data analysts from different business units. Which steps should a data analyst take to accomplish this task efficiently and securely?
    - [ ] A. Create an AWS Lambda function to process the DynamoDB stream. Decrypt the sensitive data using the same KMS key. Save the output to a restricted S3 bucket for the finance team. Create a finance table in Amazon Redshift that is accessible to the finance team only. Use the COPY command to load the data from Amazon S3 to the finance table.
    - [ ] B. Create an AWS Lambda function to process the DynamoDB stream. Save the output to a restricted S3 bucket for the finance team. Create a finance table in Amazon Redshift that is accessible to the finance team only. Use the COPY command with the IAM role that has access to the KMS key to load the data from S3 to the finance table.
    - [ ] C. Create an Amazon EMR cluster with an EMR_EC2_DefaultRole role that has access to the KMS key. Create Apache Hive tables that reference the data stored in DynamoDB and the finance table in Amazon Redshift. In Hive, select the data from DynamoDB and then insert the output to the finance table in Amazon Redshift.
    - [ ] D. Create an Amazon EMR cluster. Create Apache Hive tables that reference the data stored in DynamoDB. Insert the output to the restricted Amazon S3 bucket for the finance team. Use the COPY command with the IAM role that has access to the KMS key to load the data from Amazon S3 to the finance table in Amazon Redshift.

    <details>
       <summary>Answer</summary>

       - Option A: This approach involves creating an AWS Lambda function to process the DynamoDB stream and decrypt the sensitive data using the same AWS KMS key. The decrypted data is then saved to a restricted Amazon S3 bucket accessible only by the finance team. A dedicated finance table in Amazon Redshift, which only the finance team can access, is used to load the data from the S3 bucket using the COPY command. This option ensures that decryption and data transfer are securely handled, and access is restricted to the finance team.
       - Option B: Similar to Option A, this option also uses an AWS Lambda function to process the DynamoDB stream. However, it doesn't specify the decryption step, which is crucial since the data in DynamoDB is encrypted. The data is stored in a restricted S3 bucket, and a finance table in Amazon Redshift is used for loading the data. The COPY command utilizes an IAM role with access to the KMS key. The lack of explicit decryption step is a concern here.
       - Option C: This option proposes using an Amazon EMR cluster with an EMR_EC2_DefaultRole that has access to the KMS key. It involves creating Apache Hive tables to reference the data in DynamoDB and the finance table in Redshift. Data is selected from DynamoDB using Hive and then inserted into the finance table in Redshift. While this method could handle decryption, it introduces additional complexity and costs with the EMR cluster and might not be as straightforward as Lambda for processing streams.
       - Option D: This option also suggests using an Amazon EMR cluster, but it doesn't specify access to the KMS key in the role, which is necessary for decryption. It involves using Apache Hive tables to reference DynamoDB data and inserting the output into a restricted S3 bucket for the finance team. The data is then loaded into Redshift using the COPY command with an IAM role that has KMS access. Like Option C, it adds unnecessary complexity and lacks clarity on decryption.
       - Based on these evaluations, Option A seems to be the most suitable. It clearly outlines the decryption of data, secure storage in S3, and restricted access to the data in Amazon Redshift, ensuring both efficiency and security in line with AWS best practices.

    </details>

42. A company is building a data lake and needs to ingest data from a relational database that has time-series data. The company wants to use managed services to accomplish this. The process needs to be scheduled daily and bring incremental data only from the source into Amazon S3. What is the MOST cost-effective approach to meet these requirements?
    - [ ] A. Use AWS Glue to connect to the data source using JDBC Drivers. Ingest incremental records only using job bookmarks.
    - [ ] B. Use AWS Glue to connect to the data source using JDBC Drivers. Store the last updated key in an Amazon DynamoDB table and ingest the data using the updated key as a filter.
    - [ ] C. Use AWS Glue to connect to the data source using JDBC Drivers and ingest the entire dataset. Use appropriate Apache Spark libraries to compare the dataset, and find the delta.
    - [ ] D. Use AWS Glue to connect to the data source using JDBC Drivers and ingest the full data. Use AWS DataSync to ensure the delta only is written into Amazon S3.

    <details>
       <summary>Answer</summary>

       A.
       - A. This approach directly supports incremental data loading, minimizing data transfer and processing requirements, and aligns well with the goal of scheduling daily transfers without unnecessarily reprocessing data that has already been ingested. It also avoids the additional overhead and complexity of managing external services or custom delta processing logic.
       - B. Adds complexity and potential cost with the maintenance of an external system (DynamoDB) to track the state.
       - C. Inefficient and costly as it involves ingesting the entire dataset daily and then computing the delta, which requires significant processing resources.
       - D. Similar to Option C, this approach is inefficient for the requirement as it initially ingests the entire dataset.

    </details>

43. An Amazon Redshift database contains sensitive user data. Logging is necessary to meet compliance requirements. The logs must contain database authentication attempts, connections, and disconnections. The logs must also contain each query run against the database and record which database user ran each query. Which steps will create the required logs?
    - [ ] A. Enable Amazon Redshift Enhanced VPC Routing. Enable VPC Flow Logs to monitor traffic.
    - [ ] B. Allow access to the Amazon Redshift database using AWS IAM only. Log access using AWS CloudTrail.
    - [ ] C. Enable audit logging for Amazon Redshift using the AWS Management Console or the AWS CLI.
    - [ ] D. Enable and download audit reports from AWS Artifact.

    <details>
       <summary>Answer</summary>

       C.
       - A. VPC Flow Logs are not designed to log database query activities or user-specific actions within Amazon Redshift.
       - B. CloudTrail does not capture the internal database activities such as query execution or user-specific actions within the database.
       - C. Redshift's audit logging feature is specifically designed to track and log the types of database activities mentioned in the requirements. It will capture all authentication attempts, connections, disconnections, and details about each query, including the user who executed it. This feature is essential for compliance purposes where detailed database usage tracking is required.
       - D. It does not provide a mechanism to log specific database activities.

    </details>

44. A company that monitors weather conditions from remote construction sites is setting up a solution to collect temperature data from the following two weather stations. ✑ Station A, which has 10 sensors ✑ Station B, which has five sensors These weather stations were placed by onsite subject-matter experts. Each sensor has a unique ID. The data collected from each sensor will be collected using Amazon Kinesis Data Streams. Based on the total incoming and outgoing data throughput, a single Amazon Kinesis data stream with two shards is created. Two partition keys are created based on the station names. During testing, there is a bottleneck on data coming from Station A, but not from Station B. Upon review, it is confirmed that the total stream throughput is still less than the allocated Kinesis Data Streams throughput. How can this bottleneck be resolved without increasing the overall cost and complexity of the solution, while retaining the data collection quality requirements?
    - [ ] A. Increase the number of shards in Kinesis Data Streams to increase the level of parallelism.
    - [ ] B. Create a separate Kinesis data stream for Station A with two shards, and stream Station A sensor data to the new stream.
    - [ ] C. Modify the partition key to use the sensor ID instead of the station name.
    - [ ] D. Reduce the number of sensors in Station A from 10 to 5 sensors.

    <details>
       <summary>Answer</summary>

       C.
       - A, B. Might increase the cost since Kinesis pricing is per shard.
       - C. This approach ensures a more balanced distribution of data across the available shards, likely resolving the bottleneck without increasing costs or adding significant complexity to the setup. It leverages the existing shards more effectively by distributing the data from the larger number of sensors at Station A across both shards, rather than concentrating all of Station A's data into a single shard due to the common partition key.
       - D. Reducing sensors could compromise the data collection quality and the purpose of monitoring.

    </details>

45. Once a month, a company receives a 100 MB .csv file compressed with gzip. The file contains 50,000 property listing records and is stored in Amazon S3 Glacier. The company needs its data analyst to query a subset of the data for a specific vendor. What is the most cost-effective solution?
    - [ ] A. Load the data into Amazon S3 and query it with Amazon S3 Select.
    - [ ] B. Query the data from Amazon S3 Glacier directly with Amazon Glacier Select.
    - [ ] C. Load the data to Amazon S3 and query it with Amazon Athena.
    - [ ] D. Load the data to Amazon S3 and query it with Amazon Redshift Spectrum.

    <details>
       <summary>Answer</summary>

       B.
       - A. Requires retrieving the data from Glacier to S3, incurring data retrieval costs and potential delays due to Glacier's retrieval times.
       - B. This approach enables querying data directly within Glacier, avoiding the costs and time associated with retrieving the entire file to S3. While Glacier Select may have longer latency, it is likely acceptable given the monthly frequency of the task and the small size of the file.
       - C. Similar to Option A, involves data retrieval costs and delays.
       - D. Redshift Spectrum might be more than necessary for querying a single, small file and could incur higher costs compared to other options.

    </details>

46. A retail company is building its data warehouse solution using Amazon Redshift. As a part of that effort, the company is loading hundreds of files into the fact table created in its Amazon Redshift cluster. The company wants the solution to achieve the highest throughput and optimally use cluster resources when loading data into the company's fact table. How should the company meet these requirements?
    - [ ] A. Use multiple COPY commands to load the data into the Amazon Redshift cluster.
    - [ ] B. Use S3DistCp to load multiple files into the Hadoop Distributed File System (HDFS) and use an HDFS connector to ingest the data into the Amazon Redshift cluster.
    - [ ] C. Use LOAD commands equal to the number of Amazon Redshift cluster nodes and load the data in parallel into each node.
    - [ ] D. Use a single COPY command to load the data into the Amazon Redshift cluster.

    <details>
       <summary>Answer</summary>

       D.
       - A. Managing multiple COPY commands can be complex and might not be as efficient as other methods.
       - B. Not a direct method for loading data into Redshift, and potentially less efficient than loading directly from S3.
       - C. Manually managing data loading to align with cluster nodes can be complex and does not guarantee optimal resource use.
       - D. The COPY command is specifically designed for efficiently loading large amounts of data into Redshift. It handles parallelism and distribution of data across the cluster's nodes and slices automatically, which optimizes resource usage and throughput. This approach is straightforward, reduces complexity, and is aligned with Amazon Redshift's best practices for data loading.

    </details>

47. A data analyst is designing a solution to interactively query datasets with SQL using a JDBC connection. Users will join data stored in Amazon S3 in Apache ORC format with data stored in Amazon Elasticsearch Service (Amazon ES) and Amazon Aurora MySQL. Which solution will provide the MOST up-to-date results?
    - [ ] A. Use AWS Glue jobs to ETL data from Amazon ES and Aurora MySQL to Amazon S3. Query the data with Amazon Athena.
    - [ ] B. Use Amazon DMS to stream data from Amazon ES and Aurora MySQL to Amazon Redshift. Query the data with Amazon Redshift.
    - [ ] C. Query all the datasets in place with Apache Spark SQL running on an AWS Glue developer endpoint.
    - [ ] D. Query all the datasets in place with Apache Presto running on Amazon EMR.

    <details>
       <summary>Answer</summary>

       - A. AWS Glue ETL with Amazon Athena: AWS Glue can be used to extract, transform, and load (ETL) data from Amazon Elasticsearch Service and Aurora MySQL to Amazon S3. Amazon Athena can then be used to query this data. However, the ETL process in AWS Glue might introduce some latency, depending on the ETL job schedule. This could mean the data in S3 is not the most current compared to the source systems.
       - B. Amazon DMS with Amazon Redshift: Amazon Database Migration Service (DMS) can continuously replicate data from source databases (like Aurora MySQL) to a target like Amazon Redshift. However, DMS doesn't natively support Amazon Elasticsearch Service as a source, which is a key requirement here. While Redshift provides powerful querying capabilities, the limitation with Elasticsearch integration makes this option less suitable.
       - C. Apache Spark SQL on AWS Glue Developer Endpoint: Apache Spark SQL can query data across different data stores. Running Spark SQL on an AWS Glue developer endpoint allows querying data in place without moving it, ensuring you're working with the most current data. However, querying data directly in Amazon ES and Aurora MySQL might require additional connectors or integrations.
       - D. Apache Presto on Amazon EMR: Apache Presto is designed for querying data across multiple sources interactively. Running Presto on Amazon EMR would allow querying data in Amazon S3, Amazon Elasticsearch Service, and Amazon Aurora MySQL directly, without ETL processes, ensuring real-time access to the latest data. Presto is well-suited for this kind of federated query across different data stores.
       - Given these considerations, Option D (Apache Presto running on Amazon EMR) seems to be the most suitable for providing the most up-to-date results. It allows for interactive querying across all the mentioned data stores without the need for ETL processes, thereby ensuring that the queries are performed on the most current data available.

    </details>

48. A company developed a new elections reporting website that uses Amazon Kinesis Data Firehose to deliver full logs from AWS WAF to an Amazon S3 bucket. The company is now seeking a low-cost option to perform this infrequent data analysis with visualizations of logs in a way that requires minimal development effort. Which solution meets these requirements?
    - [ ] A. Use an AWS Glue crawler to create and update a table in the Glue data catalog from the logs. Use Athena to perform ad-hoc analyses and use Amazon QuickSight to develop data visualizations.
    - [ ] B. Create a second Kinesis Data Firehose delivery stream to deliver the log files to Amazon OpenSearch Service (Amazon Elasticsearch Service). Use Amazon ES to perform text-based searches of the logs for ad-hoc analyses and use OpenSearch Dashboards (Kibana) for data visualizations.
    - [ ] C. Create an AWS Lambda function to convert the logs into .csv format. Then add the function to the Kinesis Data Firehose transformation configuration. Use Amazon Redshift to perform ad-hoc analyses of the logs using SQL queries and use Amazon QuickSight to develop data visualizations.
    - [ ] D. Create an Amazon EMR cluster and use Amazon S3 as the data source. Create an Apache Spark job to perform ad-hoc analyses and use Amazon QuickSight to develop data visualizations.

    <details>
       <summary>Answer</summary>

       A.
       - A. Using AWS Glue to catalog the data, Athena for ad-hoc SQL-like queries, and QuickSight for visualization minimizes development effort and aligns with the need for infrequent analysis. This option is cost-effective and straightforward compared to the alternatives, which either introduce unnecessary complexity or incur higher costs for the stated requirements.
       - B. Setup and maintenance of Amazon OpenSearch Service might involve more cost and complexity.
       - C. Requires development effort to set up and maintain the Lambda function.
       - D. Setting up and managing an EMR cluster and Spark jobs requires significant development and maintenance effort.

    </details>

49. A large company has a central data lake to run analytics across different departments. Each department uses a separate AWS account and stores its data in an Amazon S3 bucket in that account. Each AWS account uses the AWS Glue Data Catalog as its data catalog. There are different data lake access requirements based on roles. Associate analysts should only have read access to their departmental data. Senior data analysts can have access in multiple departments including theirs, but for a subset of columns only. Which solution achieves these required access patterns to minimize costs and administrative tasks?
    - [ ] A. Consolidate all AWS accounts into one account. Create different S3 buckets for each department and move all the data from every account to the central data lake account. Migrate the individual data catalogs into a central data catalog and apply fine-grained permissions to give to each user the required access to tables and databases in AWS Glue and Amazon S3.
    - [ ] B. Keep the account structure and the individual AWS Glue catalogs on each account. Add a central data lake account and use AWS Glue to catalog data from various accounts. Configure cross-account access for AWS Glue crawlers to scan the data in each departmental S3 bucket to identify the schema and populate the catalog. Add the senior data analysts into the central account and apply highly detailed access controls in the Data Catalog and Amazon S3.
    - [ ] C. Set up an individual AWS account for the central data lake. Use AWS Lake Formation to catalog the cross-account locations. On each individual S3 bucket, modify the bucket policy to grant S3 permissions to the Lake Formation service-linked role. Use Lake Formation permissions to add fine-grained access controls to allow senior analysts to view specific tables and columns.
    - [ ] D. Set up an individual AWS account for the central data lake and configure a central S3 bucket. Use an AWS Lake Formation blueprint to move the data from the various buckets into the central S3 bucket. On each individual bucket, modify the bucket policy to grant S3 permissions to the Lake Formation service-linked role. Use Lake Formation permissions to add fine-grained access controls for both associate and senior analysts to view specific tables and columns.

    <details>
       <summary>Answer</summary>

       C.
       - A. Consolidating all accounts into one might not be feasible or desirable due to organizational, security, or billing reasons. Significant effort and potential risk involved in migrating all data and catalogs to a single account.
       - B. Managing cross-account permissions and cataloging can be complex. Might not provide the most streamlined approach for fine-grained access control, particularly for column-level access.
       - C. This approach avoids the complexities and potential risks associated with consolidating all accounts into one (Option A) and the data movement required in Option D. It also addresses the need for detailed access controls more directly than Option B, which might involve more complexity in managing cross-account permissions without the specific benefits of Lake Formation.
       - D. Moving data to a central bucket can be a significant undertaking and may incur data transfer costs.

    </details>

50. A company wants to improve user satisfaction for its smart home system by adding more features to its recommendation engine. Each sensor asynchronously pushes its nested JSON data into Amazon Kinesis Data Streams using the Kinesis Producer Library (KPL) in Java. Statistics from a set of failed sensors showed that, when a sensor is malfunctioning, its recorded data is not always sent to the cloud. The company needs a solution that offers near-real-time analytics on the data from the most updated sensors. Which solution enables the company to meet these requirements?
    - [ ] A. Set the RecordMaxBufferedTime property of the KPL to "1" to disable the buffering on the sensor side. Use Kinesis Data Analytics to enrich the data based on a company-developed anomaly detection SQL script. Push the enriched data to a fleet of Kinesis data streams and enable the data transformation feature to flatten the JSON file. Instantiate a dense storage Amazon Redshift cluster and use it as the destination for the Kinesis Data Firehose delivery stream.
    - [ ] B. Update the sensors code to use the PutRecord/PutRecords call from the Kinesis Data Streams API with the AWS SDK for Java. Use Kinesis Data Analytics to enrich the data based on a company-developed anomaly detection SQL script. Direct the output of KDA application to a Kinesis Data Firehose delivery stream, enable the data transformation feature to flatten the JSON file, and set the Kinesis Data Firehose destination to an Amazon OpenSearch Service (Amazon Elasticsearch Service) cluster.
    - [ ] C. Set the RecordMaxBufferedTime property of the KPL to "0" to disable the buffering on the sensor side. Connect for each stream a dedicated Kinesis Data Firehose delivery stream and enable the data transformation feature to flatten the JSON file before sending it to an Amazon S3 bucket. Load the S3 data into an Amazon Redshift cluster.
    - [ ] D. Update the sensors code to use the PutRecord/PutRecords call from the Kinesis Data Streams API with the AWS SDK for Java. Use AWS Glue to fetch and process data from the stream using the Kinesis Client Library (KCL). Instantiate an Amazon Elasticsearch Service cluster and use AWS Lambda to directly push data into it.

    <details>
       <summary>Answer</summary>

       B.
       - A. The use of dense storage Redshift cluster might be overkill for this use case and could lead to higher costs. Flattening JSON in Kinesis streams might add complexity.
       - B.  It ensures immediate data transfer and leverages Kinesis Data Analytics for real-time processing and anomaly detection. Directing the output to Kinesis Data Firehose, which then sends data to Amazon OpenSearch Service (formerly Elasticsearch), allows for effective searching and visualization of the data. This option provides a balance of real-time data processing and powerful analytics capabilities without overly complex or costly infrastructure changes.
       - C. Lacks the real-time analytics capabilities before the data reaches S3/Redshift.
       - D. AWS Glue might not be the best tool for real-time streaming data processing.

    </details>

51. A global company has different sub-organizations, and each sub-organization sells its products and services in various countries. The company's senior leadership wants to quickly identify which sub-organization is the strongest performer in each country. All sales data is stored in Amazon S3 in Parquet format. Which approach can provide the visuals that senior leadership requested with the least amount of effort?
    - [ ] A. Use Amazon QuickSight with Amazon Athena as the data source. Use heat maps as the visual type.
    - [ ] B. Use Amazon QuickSight with Amazon S3 as the data source. Use heat maps as the visual type.
    - [ ] C. Use Amazon QuickSight with Amazon Athena as the data source. Use pivot tables as the visual type.
    - [ ] D. Use Amazon QuickSight with Amazon S3 as the data source. Use pivot tables as the visual type.

    <details>
       <summary>Answer</summary>

       A.

    </details>

52. A company has 1 million scanned documents stored as image files in Amazon S3. The documents contain typewritten application forms with information including the applicant first name, applicant last name, application date, application type, and application text. The company has developed a machine learning algorithm to extract the metadata values from the scanned documents. The company wants to allow internal data analysts to analyze and find applications using the applicant name, application date, or application text. The original images should also be downloadable. Cost control is secondary to query performance. Which solution organizes the images and metadata to drive insights while meeting the requirements?
    - [ ] A. For each image, use object tags to add the metadata. Use Amazon S3 Select to retrieve the files based on the applicant name and application date.
    - [ ] B. Index the metadata and the Amazon S3 location of the image file in Amazon Elasticsearch Service. Allow the data analysts to use Kibana to submit queries to the Elasticsearch cluster.
    - [ ] C. Store the metadata and the Amazon S3 location of the image file in an Amazon Redshift table. Allow the data analysts to run ad-hoc queries on the table.
    - [ ] D. Store the metadata and the Amazon S3 location of the image files in an Apache Parquet file in Amazon S3, and define a table in the AWS Glue Data Catalog. Allow data analysts to use Amazon Athena to submit custom queries.

    <details>
       <summary>Answer</summary>

       B.

    </details>

53. A mobile gaming company wants to capture data from its gaming app and make the data available for analysis immediately. The data record size will be approximately 20 KB. The company is concerned about achieving optimal throughput from each device. Additionally, the company wants to develop a data stream processing application with dedicated throughput for each consumer. Which solution would achieve this goal?
    - [ ] A. Have the app call the PutRecords API to send data to Amazon Kinesis Data Streams. Use the enhanced fan-out feature while consuming the data.
    - [ ] B. Have the app call the PutRecordBatch API to send data to Amazon Kinesis Data Firehose. Submit a support case to enable dedicated throughput on the account.
    - [ ] C. Have the app use Amazon Kinesis Producer Library (KPL) to send data to Kinesis Data Firehose. Use the enhanced fan-out feature while consuming the data.
    - [ ] D. Have the app call the PutRecords API to send data to Amazon Kinesis Data Streams. Host the stream-processing application on Amazon EC2 with Auto Scaling.

    <details>
       <summary>Answer</summary>

       A.

    </details>

54. A marketing company wants to improve its reporting and business intelligence capabilities. During the planning phase, the company interviewed the relevant stakeholders and discovered that: ✑ The operations team reports are run hourly for the current month's data. ✑ The sales team wants to use multiple Amazon QuickSight dashboards to show a rolling view of the last 30 days based on several categories. The sales team also wants to view the data as soon as it reaches the reporting backend. ✑ The finance team's reports are run daily for last month's data and once a month for the last 24 months of data. Currently, there is 400 TB of data in the system with an expected additional 100 TB added every month. The company is looking for a solution that is as cost- effective as possible. Which solution meets the company's requirements?
    - [ ] A. Store the last 24 months of data in Amazon Redshift. Configure Amazon QuickSight with Amazon Redshift as the data source.
    - [ ] B. Store the last 2 months of data in Amazon Redshift and the rest of the months in Amazon S3. Set up an external schema and table for Amazon Redshift Spectrum. Configure Amazon QuickSight with Amazon Redshift as the data source.
    - [ ] C. Store the last 24 months of data in Amazon S3 and query it using Amazon Redshift Spectrum. Configure Amazon QuickSight with Amazon Redshift Spectrum as the data source.
    - [ ] D. Store the last 2 months of data in Amazon Redshift and the rest of the months in Amazon S3. Use a long-running Amazon EMR with Apache Spark cluster to query the data as needed. Configure Amazon QuickSight with Amazon EMR as the data source.

    <details>
       <summary>Answer</summary>

       B.

    </details>

55. A media company wants to perform machine learning and analytics on the data residing in its Amazon S3 data lake. There are two data transformation requirements that will enable the consumers within the company to create reports: ✑ Daily transformations of 300 GB of data with different file formats landing in Amazon S3 at a scheduled time. ✑ One-time transformations of terabytes of archived data residing in the S3 data lake. Which combination of solutions cost-effectively meets the company's requirements for transforming the data? (Choose three.)
    - [ ] A. For daily incoming data, use AWS Glue crawlers to scan and identify the schema.
    - [ ] B. For daily incoming data, use Amazon Athena to scan and identify the schema.
    - [ ] C. For daily incoming data, use Amazon Redshift to perform transformations.
    - [ ] D. For daily incoming data, use AWS Glue workflows with AWS Glue jobs to perform transformations.
    - [ ] E. For archived data, use Amazon EMR to perform data transformations.
    - [ ] F. For archived data, use Amazon SageMaker to perform data transformations.

    <details>
       <summary>Answer</summary>

       ADE.

    </details>

56. A hospital uses wearable medical sensor devices to collect data from patients. The hospital is architecting a near-real-time solution that can ingest the data securely at scale. The solution should also be able to remove the patient's protected health information (PHI) from the streaming data and store the data in durable storage. Which solution meets these requirements with the least operational overhead?
    - [ ] A. Ingest the data using Amazon Kinesis Data Streams, which invokes an AWS Lambda function using Kinesis Client Library (KCL) to remove all PHI. Write the data in Amazon S3.
    - [ ] B. Ingest the data using Amazon Kinesis Data Firehose to write the data to Amazon S3. Have Amazon S3 trigger an AWS Lambda function that parses the sensor data to remove all PHI in Amazon S3.
    - [ ] C. Ingest the data using Amazon Kinesis Data Streams to write the data to Amazon S3. Have the data stream launch an AWS Lambda function that parses the sensor data and removes all PHI in Amazon S3.
    - [ ] D. Ingest the data using Amazon Kinesis Data Firehose to write the data to Amazon S3. Implement a transformation AWS Lambda function that parses the sensor data to remove all PHI.

    <details>
       <summary>Answer</summary>

       D.

    </details>

57. A company is migrating its existing on-premises ETL jobs to Amazon EMR. The code consists of a series of jobs written in Java. The company needs to reduce overhead for the system administrators without changing the underlying code. Due to the sensitivity of the data, compliance requires that the company use root device volume encryption on all nodes in the cluster. Corporate standards require that environments be provisioned though AWS CloudFormation when possible. Which solution satisfies these requirements?
    - [ ] A. Install open-source Hadoop on Amazon EC2 instances with encrypted root device volumes. Configure the cluster in the CloudFormation template.
    - [ ] B. Use a CloudFormation template to launch an EMR cluster. In the configuration section of the cluster, define a bootstrap action to enable TLS.
    - [ ] C. Create a custom AMI with encrypted root device volumes. Configure Amazon EMR to use the custom AMI using the CustomAmild property in the CloudFormation template.
    - [ ] D. Use a CloudFormation template to launch an EMR cluster. In the configuration section of the cluster, define a bootstrap action to encrypt the root device volume of every node.

    <details>
       <summary>Answer</summary>

       C.

    </details>

58. A transportation company uses IoT sensors attached to trucks to collect vehicle data for its global delivery fleet. The company currently sends the sensor data in small .csv files to Amazon S3. The files are then loaded into a 10-node Amazon Redshift cluster with two slices per node and queried using both Amazon Athena and Amazon Redshift. The company wants to optimize the files to reduce the cost of querying and also improve the speed of data loading into the Amazon Redshift cluster. Which solution meets these requirements?
    - [ ] A. Use AWS Glue to convert all the files from .csv to a single large Apache Parquet file. COPY the file into Amazon Redshift and query the file with Athena from Amazon S3.
    - [ ] B. Use Amazon EMR to convert each .csv file to Apache Avro. COPY the files into Amazon Redshift and query the file with Athena from Amazon S3.
    - [ ] C. Use AWS Glue to convert the files from .csv to a single large Apache ORC file. COPY the file into Amazon Redshift and query the file with Athena from Amazon S3.
    - [ ] D. Use AWS Glue to convert the files from .csv to Apache Parquet to create 20 Parquet files. COPY the files into Amazon Redshift and query the files with Athena from Amazon S3.

    <details>
       <summary>Answer</summary>

       D.

    </details>

59. An online retail company with millions of users around the globe wants to improve its ecommerce analytics capabilities. Currently, clickstream data is uploaded directly to Amazon S3 as compressed files. Several times each day, an application running on Amazon EC2 processes the data and makes search options and reports available for visualization by editors and marketers. The company wants to make website clicks and aggregated data available to editors and marketers in minutes to enable them to connect with users more effectively. Which options will help meet these requirements in the MOST efficient way? (Choose two.)
    - [ ] A. Use Amazon Kinesis Data Firehose to upload compressed and batched clickstream records to Amazon Elasticsearch Service.
    - [ ] B. Upload clickstream records to Amazon S3 as compressed files. Then use AWS Lambda to send data to Amazon Elasticsearch Service from Amazon S3.
    - [ ] C. Use Amazon Elasticsearch Service deployed on Amazon EC2 to aggregate, filter, and process the data. Refresh content performance dashboards in near-real time.
    - [ ] D. Use Kibana to aggregate, filter, and visualize the data stored in Amazon Elasticsearch Service. Refresh content performance dashboards in near-real time.
    - [ ] E. Upload clickstream records from Amazon S3 to Amazon Kinesis Data Streams and use a Kinesis Data Streams consumer to send records to Amazon Elasticsearch Service.

    <details>
       <summary>Answer</summary>

       BD.

    </details>

60. A company is streaming its high-volume billing data (100 MBps) to Amazon Kinesis Data Streams. A data analyst partitioned the data on account_id to ensure that all records belonging to an account go to the same Kinesis shard and order is maintained. While building a custom consumer using the Kinesis Java SDK, the data analyst notices that, sometimes, the messages arrive out of order for account_id. Upon further investigation, the data analyst discovers the messages that are out of order seem to be arriving from different shards for the same account_id and are seen when a stream resize runs. What is an explanation for this behavior and what is the solution?
    - [ ] A. There are multiple shards in a stream and order needs to be maintained in the shard. The data analyst needs to make sure there is only a single shard in the stream and no stream resize runs.
    - [ ] B. The hash key generation process for the records is not working correctly. The data analyst should generate an explicit hash key on the producer side so the records are directed to the appropriate shard accurately.
    - [ ] C. The records are not being received by Kinesis Data Streams in order. The producer should use the PutRecords API call instead of the PutRecord API call with the SequenceNumberForOrdering parameter.
    - [ ] D. The consumer is not processing the parent shard completely before processing the child shards after a stream resize. The data analyst should process the parent shard completely first before processing the child shards.

    <details>
       <summary>Answer</summary>

       D.

    </details>

61. A media analytics company consumes a stream of social media posts. The posts are sent to an Amazon Kinesis data stream partitioned on user_id. An AWS Lambda function retrieves the records and validates the content before loading the posts into an Amazon Elasticsearch cluster. The validation process needs to receive the posts for a given user in the order they were received. A data analyst has noticed that, during peak hours, the social media platform posts take more than an hour to appear in the Elasticsearch cluster. What should the data analyst do reduce this latency?
    - [ ] A. Migrate the validation process to Amazon Kinesis Data Firehose.
    - [ ] B. Migrate the Lambda consumers from standard data stream iterators to an HTTP/2 stream consumer.
    - [ ] C. Increase the number of shards in the stream.
    - [ ] D. Configure multiple Lambda functions to process the stream.

    <details>
       <summary>Answer</summary>

       C.

    </details>

62. A company launched a service that produces millions of messages every day and uses Amazon Kinesis Data Streams as the streaming service. The company uses the Kinesis SDK to write data to Kinesis Data Streams. A few months after launch, a data analyst found that write performance is significantly reduced. The data analyst investigated the metrics and determined that Kinesis is throttling the write requests. The data analyst wants to address this issue without significant changes to the architecture. Which actions should the data analyst take to resolve this issue? (Choose two.)
    - [ ] A. Increase the Kinesis Data Streams retention period to reduce throttling.
    - [ ] B. Replace the Kinesis API-based data ingestion mechanism with Kinesis Agent.
    - [ ] C. Increase the number of shards in the stream using the UpdateShardCount API.
    - [ ] D. Choose partition keys in a way that results in a uniform record distribution across shards.
    - [ ] E. Customize the application code to include retry logic to improve performance.

    <details>
       <summary>Answer</summary>

       CD.

    </details>

63. A smart home automation company must efficiently ingest and process messages from various connected devices and sensors. The majority of these messages are comprised of a large number of small files. These messages are ingested using Amazon Kinesis Data Streams and sent to Amazon S3 using a Kinesis data stream consumer application. The Amazon S3 message data is then passed through a processing pipeline built on Amazon EMR running scheduled PySpark jobs. The data platform team manages data processing and is concerned about the efficiency and cost of downstream data processing. They want to continue to use PySpark. Which solution improves the efficiency of the data processing jobs and is well architected?
    - [ ] A. Send the sensor and devices data directly to a Kinesis Data Firehose delivery stream to send the data to Amazon S3 with Apache Parquet record format conversion enabled. Use Amazon EMR running PySpark to process the data in Amazon S3.
    - [ ] B. Set up an AWS Lambda function with a Python runtime environment. Process individual Kinesis data stream messages from the connected devices and sensors using Lambda.
    - [ ] C. Launch an Amazon Redshift cluster. Copy the collected data from Amazon S3 to Amazon Redshift and move the data processing jobs from Amazon EMR to Amazon Redshift.
    - [ ] D. Set up AWS Glue Python jobs to merge the small data files in Amazon S3 into larger files and transform them to Apache Parquet format. Migrate the downstream PySpark jobs from Amazon EMR to AWS Glue.

    <details>
       <summary>Answer</summary>

       D.

    </details>

64. A large financial company is running its ETL process. Part of this process is to move data from Amazon S3 into an Amazon Redshift cluster. The company wants to use the most cost-efficient method to load the dataset into Amazon Redshift. Which combination of steps would meet these requirements? (Choose two.)
    - [ ] A. Use the COPY command with the manifest file to load data into Amazon Redshift.
    - [ ] B. Use S3DistCp to load files into Amazon Redshift.
    - [ ] C. Use temporary staging tables during the loading process.
    - [ ] D. Use the UNLOAD command to upload data into Amazon Redshift.
    - [ ] E. Use Amazon Redshift Spectrum to query files from Amazon S3.

    <details>
       <summary>Answer</summary>

       AC.

    </details>

65. A university intends to use Amazon Kinesis Data Firehose to collect JSON-formatted batches of water quality readings in Amazon S3. The readings are from 50 sensors scattered across a local lake. Students will query the stored data using Amazon Athena to observe changes in a captured metric over time, such as water temperature or acidity. Interest has grown in the study, prompting the university to reconsider how data will be stored. Which data format and partitioning choices will MOST significantly reduce costs? (Choose two.)
    - [ ] A. Store the data in Apache Avro format using Snappy compression.
    - [ ] B. Partition the data by year, month, and day.
    - [ ] C. Store the data in Apache ORC format using no compression.
    - [ ] D. Store the data in Apache Parquet format using Snappy compression.
    - [ ] E. Partition the data by sensor, year, month, and day.

    <details>
       <summary>Answer</summary>

       BD.

    </details>

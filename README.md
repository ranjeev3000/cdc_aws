# Change Data Capture (CDC) using AWS Services
<ul>
  <li><strong>1. OverView: </strong></li>
  <p>The goal of this project is to implement Change Data Capture using AWS services such as RDS, DMS, AWS Glue, Lambda, and S3. The process involves capturing changes made to a source database hosted on Amazon RDS, transforming the data using AWS Glue with PySpark code, and storing the final change information in an S3 bucket.</p>
  <li><strong>2. Prerequisites: </strong></li>
  <p>
    Before starting the project, ensure that you have the following:
<ul>
<li>An AWS account with appropriate permissions.</li>
<li>An Amazon RDS instance set up as the source database.</li>
<li>DMS (Database Migration Service) configured to replicate changes from the source database to the destination. </li>
<li>A temporary S3 bucket to store the replicated data. </li>
<li>An AWS Glue job with PySpark code for data transformation. </li>
<li>An S3 bucket to store the final change information. </li>
</ul>
  </p>
  <li><strong>3. Process: </strong></li>
  <p>
  <ul>
    <li>Set up the source endpoint in DMS: Configure the source endpoint in DMS to connect to the source RDS instance. Provide the necessary connection details such as database credentials, endpoint URL, and port.</li>
    <li>Set up the destination endpoint in DMS: Configure the destination endpoint in DMS to connect to the temporary S3 bucket. Specify the required S3 bucket details and credentials.</li>
    <li>Create a DMS replication task: Create a replication task in DMS to define the source and destination endpoints, replication settings, and table mappings. Select the tables you want to capture changes for.</li>
    <li>Start the DMS replication task: Once the replication task is set up, start it to begin capturing changes from the source database. DMS continuously replicates changes to the temporary S3 bucket.</li>
    <li>Configure a Lambda trigger function: Set up a Lambda function that triggers whenever new data is written to the temporary S3 bucket. This function will be responsible for initiating the AWS Glue job.</li>
    <li>Create an AWS Glue job: Develop an AWS Glue job using PySpark code to transform the replicated data stored in the temporary S3 bucket. Write code to perform any necessary data cleansing, filtering, or enrichment as required.</li>
    <li>Execute the AWS Glue job: Trigger the AWS Glue job manually or configure it to run automatically whenever new data is available in the temporary S3 bucket. The job will process the replicated data and generate the final change information.</li>
    <li>Store final change information in an S3 bucket: Once the AWS Glue job completes, it will generate the transformed data. Store this data in the specified S3 bucket to make it available for further analysis or downstream processes.</li>
  </ul>
  </p>
  <li> <strong>4. References:</strong></li>
  <ol type="1">
<li>AWS Documentation:</li>
    <ul>
      <li><a href="https://docs.aws.amazon.com/rds/index.html">AWS RDS Documentation</a></li>
      <li><a href="https://docs.aws.amazon.com/dms/index.html">AWS DMS Documentation</a></li>
      <li><a href="https://docs.aws.amazon.com/lambda/index.html">AWS Lambda Documentation</a></li>
      <li><a href="https://docs.aws.amazon.com/glue/index.html">AWS Glue Documentation</a></li>
      <li><a href="https://docs.aws.amazon.com/s3/index.html">AWS S3 Documentation</a></li>
    </ul>
<li>Tutorials and Guides:</li>
<ul>
  <li><a href="https://aws.amazon.com/getting-started/hands-on/move-to-managed/migrate-sql-server-to-amazon-rds/">AWS Database Migration Service (DMS) Step-by-Step Migration Guide</a></li>
  <li><a href="https://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-samples-tutorial.html">AWS Glue PySpark ETL Tutorial</a></li>
  <li><a href="https://docs.aws.amazon.com/lambda/latest/dg/welcome.html">AWS Lambda Developer Guide</a></li>
</ul>
   <li> Blogs and Articles:</li> 
    <ul>
      <li><a href="https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Task.CDC.html">Change Data Capture using AWS DMS</a></li>
      <li><a href="https://aws.amazon.com/blogs/big-data/build-and-automate-a-serverless-data-lake-using-an-aws-glue-trigger-for-the-data-catalog-and-etl-jobs/">Building a Serverless Data Pipeline with AWS Glue and AWS Lambda</a></li>
    </ul>
    <li>GitHub Repositories and Examples:</li>
    <ul>
      <li><a href="https://github.com/aws-samples/aws-glue-samples">AWS Samples - AWS Glue Examples</a></li>
      <li><a href="https://github.com/awslabs/aws-database-migration-samples">AWS Labs - DMS Sample Code</a></li>
    </ul>
  </ol>
</ul>


![image](https://github.com/ranjeev3000/cdc_aws/assets/73913671/1091f58f-b317-4b23-b53f-69c593cb485f)


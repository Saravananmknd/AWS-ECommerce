# AWS-ECommerce
Personal project<br />

# AWS Project for e-commerce company website

# Structure of the overall system<br />
 
<img src="https://user-images.githubusercontent.com/100179829/172836644-beb54d83-1230-4949-a2b0-45eada0e9927.jpg" width="1000"><br />

This project have 5 parts of different for a e-commerce company.<br /><br />

# Part 1: Order History app
![Picture1](https://user-images.githubusercontent.com/100179829/172833888-9680fae4-ab38-4efd-a4cc-dc5a96ed1b3c.jpg)<br />
Server logs are generated with the help of EC2 instance and forwarded the logs to Amazon DynamoDB with the help of Amazon kinesis Data Stream and Lambda, So the Client app can access the History data from DynamoDB.<br />
# Part 2: Product recommendation
![Picture2](https://user-images.githubusercontent.com/100179829/172834101-7b0c2720-ab46-457b-ba1f-3902517370c6.jpg)<br />
Server logs are generated with the help of EC2 instance. Amazon Kinesis Data Firehose will stream the data to the data lake, which is hosted in Amazon S3, the data lake acts as a data source to the EMR cluster. By using the help of EMR cluster we run the Apache spark to give a product recommendation to the users. <br />  
# Part 3: Transaction rate alarm
![Picture3](https://user-images.githubusercontent.com/100179829/172834196-bfa5723e-7b4c-4b6e-a6f9-39bc00196ad7.jpg)<br />
This part of the system helps to alert if we have unexpected rate of orders come to our server. We used Kinesis data stream and amazon kinesis data analytics to monitor our incoming orders. And used a Lambda function to fire off alarms using Amazon SNS to customer cell phone when something unusual happens. <br />
# Part 4: Near-real-time log analysis
![Picture4](https://user-images.githubusercontent.com/100179829/172837456-118d470b-9ab1-42d6-b82e-efaa6a0cb505.jpg)<br />
In this part of the model, we analyzed server log data in near real-time for operational purpose. For this requirement, we will use Kinesis Firehose to pump Apache log data directly into the Amazon elastic search service, where we can easily query that data and build dashboards for it using Cabana.<br />
# Part 5: Data warehousing & visualization
![Picture5](https://user-images.githubusercontent.com/100179829/172837522-bf85e14b-70f6-45ea-99bd-60f34738967f.jpg)<br />
Finally, we will cover the data warehousing and visualization that we need for business analysis purposes by using AWS glue, Athena, Redshift and QuickSight on top of our S3 data lake.<br />


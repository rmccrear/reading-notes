# AWS API Gateway - Dyanamo - Lambda

## AWS API Gateway

AWS API Gateway lets us specify a set of routes that will trigger AWS Lambda functions. This can turn a lambda function into a webserver. There are two ways to approach this. One is to have one route set to one Lambda function. Another is for the API to be set to send all (or some) of your routes to one Lambda function and let the lambda function handle routing with a framework like Express. AWS APIs can can integrate with other AWS services like S3 as well.

## AWS DyanamoDB

DynamoDB is a managed database from AWS. It is a document-oriented database like MongoDB. It is able to handle very large sets of data. Instead of a primary key, it has a partition key. One of the reasons it can handle so much data is that it can partition its data across hardware. The partition key will help to make sure similar data can be retrieved quickly because the documents with the same partition key will be near each other on hardware. A secondary `sort key` can be provided to better organize the data. Finally, doing a query on the remaining data will be possible since the scale has been reduced by the partition key and sort keys. (reference: aws)[https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.Partitions.html]

MongoDB also uses the same strategy in its `shard key`. Once the database grows beyond one machine, MongoDB can use its shard key to ensure that data that is frequently accessed together is stored on the same hardware. The shard key can be a single key or a collection of keys. (reference: mongodb)[https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.Partitions.html]

An example of when a NoSQL database might be more performant is something with a simple index, but a voluminous amount of data, like medical data associated with different experiments. Each experiment would have the same `shard key` or `partition key` so that they can be accessed together quickly. Then there would be other keys that could be searched on within that subset of data.

## Dynamoose


DyanamoDB has compatibility with MongoDB. But it also has its one Mongoose-like library called Dynamoose. If you are familiar with Mongoose, Dyanamoose will be easy to get started with. Dyanamoose has suport for DynomoDB specific features like DynomoDB transactions and AWS mulit-region support. (reference: dynamoose.js)[https://dynamoosejs.com/getting_started/Introduction]


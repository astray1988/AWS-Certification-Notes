Application Service summary
===========================

SQS
---

-	Message queue. Pull based queue.
-	Messages are 256 KB in size
-	Message can be kept in the queue from 1 minute to 14 days. The default is 4 days.
-	The visibility Time out is the amount of time that the message is invisible in the SQS queue after a reader picks up that message. Provided the job is processed before the visibility time out expires, the message will then be deleted from the queue. If the job is not processed within that time, the message will become visible again and another reader will process it. This could result in the same message being delivered twice.
-	Visibility time out maximum is 12 hours.(Job runs more than 12 hours, SQS maybe not a good solution) -
-	SQS guarantees that your messages will be processed at least once.
-	Amazon SQS long polling is a way to retrieve messages from your Amazon SQS queues. While the regular short polling returns immediately, even if the message queue being polled is empty, long polling doesn't return a response until a message arrives in the message queue, or the long poll times out.
-	Queue's can either be standard or FIFO

SWF vs SQS
----------

-	SQS has a retention period of 14 days, SWF up to 1 year for workflow executions.
-	Amazon SWF presents a task-oriented API, whereas Amazon SQS offers a message-oriented API. e.g. SWF, amazon fulfil orders.
-	Amazon SWF ensures that a task is assigned only once and is never duplicated. With Amazon SQS, you need to handle duplicated messages and may also need to ensure that a message is processed only once.
-	Amazon SWF keeps track of all the tasks and events in an application. With Amazon SQS, you need to implement your own application-level tracking, especially if your application uses multiple queues.

SWF Actors
----------

-	Workflow Starters: an application that can initiate(start) a workflow. Could be your e-commerce website when placing an order or a mobile app searching for bus times.
-	Deciders: Control the flow of activity tasks in a workflow execution. If someting has finished in a workflow(or fails) a Decider decides what to do next.
-	Activity Workers: Carry out the activity tasks.

SNS
---

### SNS Subscribers

-	HTTP
-	HTTPS
-	Email
-	Email -JSON
-	SQS
-	application
-	Lambda

SQS vs SNS
----------

-	Both messaging services in aws
-	SNS: Push, SQS: Pull

Elastic Transcoder
------------------

Media transcoder in the cloud, support multiple devices format.

Kinesis
-------

-	Kinesis Streams: split into shards.
-	Kinesis Firehose: send straign to S3, no shards.
-	Kinesis Analytics: Always to do SQL query. Send data to Redshift/S3/ElasticSearch

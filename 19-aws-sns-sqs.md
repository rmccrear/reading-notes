# AWS SQS asd SNS

SNS is a pub/sub service. It is used to send messages in a fan pattern one or more publishers to subscribers.

SQS is a queueing system that can be used with SNS to ensure that the intended subscribers get the messages sent. The pattern than enables this is as follows. The SNS service aggregates the published messages and pushes them out to subscribers. Each client has a dedicated SQS queue for it to listen or poll to ensure that the message is received event if the client is not connected at the moment. So the system looks like [SNS] --> [SQS] --> [CLIENT].



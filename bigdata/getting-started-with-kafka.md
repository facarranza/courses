Getting started with Kafka
============================

#### Create a topic: 
```bash
kafka-topics --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
```
####Confirm the topic is created:
```bash
kafka-topics --list --zookeeper localhost:2181
```

#### Produce a message
Focus on the fourth terminal window again and type:
```bash
kafka-console-producer --broker-list localhost:9092 --topic test
```
Press enter. No feedback appears; the cursor sits blinking and waiting for your input.

Type a message and press enter:
	Hello World!

#### Consume a message
```bash
kafka-console-consumer --bootstrap-server localhost:9092 --topic test --from-beginning
```
Confirm that the previously posted message has been consumed.

#### Remove the consumer offset registrations.
```bash
kafka-consumer-groups --delete --zookeeper localhost:2181 --topic test
```
#### Remove the topic
```bash
kafka-topics --delete --zookeeper localhost:2181 --topic test
```
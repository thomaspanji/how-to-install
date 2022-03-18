# Apache Kafka

Kafka is a distributed event streaming platform that lets you read, write, store, and process events (also called records or messages) across many machines.

## Installation
Steps to install Apache Kafka in your local machine:

1. Install Java. Here is [the tutorial](../README.md#install-java).
2. Download the binary file of Kafka from this [link](https://kafka.apache.org/downloads).
![kafka-download](/img/kafka-download-page.png)
3. Open a terminal and move to your download folder. Then extract the file using command `tar -zxvf kafka_2.13-3.1.0.tgz`
4. (Optional) Move the installed folder to your home directory and rename it. Type the command `mv kafka_2.13-3.1.0 /home/kafka`


## Usage

Kafka can be launched directly from the command line. To start it, you must run the Zookeeper cluster before.

Move to your Kafka directory (e.g. `/home/kafka`). Then type

`zookeeper-server-start.sh config/zookeeper.properties`

This will run the Zookeeper cluster with default configurations.

Open a new terminal and launch Kafka,

`kafka-server-start.sh config/server.properties`

### Create a topic

First thing to do is create a topic before writing the events. Open another terminal and run the command to create a topic named `test-events`.

`kafka-topics.sh --create --topic test-events --bootstrap-server localhost:9092`

All of Kafka's command line tools have additional options. Run the `kafka-topics.sh` command without any arguments to display usage information. For example, it can show details about a topic

`kafka-topics.sh --describe --topic test-events --bootstrap-server localhost:9092`

### Write some events into the topic

A Kafka client communicates with the Kafka brokers via the network for writing (or reading) events. Once received, the brokers will store the events in a durable and fault-tolerant  manner for as long as you need—even forever.

Run the console producer client to write a few events into your topic. By default, each line you enter will result in a separate event being written to the topic.

`kafka-console-producer.sh --topic test-events --bootstrap-server localhost:9092`

If succeeded, it will prompt for input. You can type anything to the console.

### Read the events

Open another terminal and run console consumer client to read the events created before.

`kafka-console-consumer.sh --topic test-events --from-beginning --bootstrap-server localhost:9092`

### Terminate the Kafka environment

1. Stop producer and consumer client, `Ctrl + C`.
2. Stop the Kafka broker, `Ctrl + C`.
3. Stop the Zookeeper server, `Ctrl + C`.

If you also want to delete any data of your local Kafka environment including any events you have created along the way, run this command

`rm -rf /tmp/kafka-logs /tmp/zookeeper`
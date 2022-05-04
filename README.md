# Application was made using:

* Java 17
* maven
* Kafka 3.1.0
* Docker

# Kafka Overview


# Starting kafka

You will need two Docker images to get Kafka running:

* wurstmeister/zookeeper
* wurstmeister/kafka

Execute the following command to pull the images and create containers:
```bash
docker-compose up -d
```

### Run Kafka Commands inside the container
```bash
## List Brokers
docker exec -ti kafka /usr/bin/broker-list.sh

## List Topics
docker exec -ti kafka /opt/kafka/bin/kafka-topics.sh --list --zookeeper zookeeper:2181

## Create a Topic
docker exec -ti kafka /opt/kafka/bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic test

## Check messages sent for a specifying a topic 
docker exec -ti kafka /opt/kafka/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic ECOMMERCE_NEW_ORDER --from-beginning

# reference: https://gist.github.com/DevoKun/01b6c9963d5508579f4cbd75d52640a9#run-kafka-commands-inside-the-container
```

# Create a topic

# Produce a message

# Get topic statistics

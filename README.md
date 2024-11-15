# Spring Boot Kafka Messaging Application

This project is a Spring Boot application demonstrating how to produce and consume messages using Apache Kafka. It includes two controllers for publishing messages: one for simple text messages and another for JSON-formatted messages. It also contains producers and consumers for handling these messages via Kafka.

## Features
- T**ext Messaging**: Send and receive plain text messages.
- **JSON Messaging**: Send and receive JSON-formatted messages representing a User entity.
- **Kafka Topic Configuration**: Topics are configured for both text and JSON message handling.

## Setup
#### Prerequisites
- **Apache Kafka**: **Ensure Kafka is running locally**.
- **Spring Boot**: This project is based on Spring Boot, so Maven is used for dependency management.

## Publish a Text Message
- Use the following endpoint to send a text message to Kafka:

Endpoint: GET `http://localhost:8080/api/v1/kafka/publish?message=yash`
<br><br>
<img width="1512" alt="image" src="https://github.com/user-attachments/assets/16caf9f6-f4b1-40f0-8629-61be07b38c80">

## Publish a JSON Message
- Use the following endpoint to send a JSON message representing a User to Kafka:

Endpoint: POST `http://localhost:8080/api/v1/kafka/publish`
<br><br>
<img width="1461" alt="image" src="https://github.com/user-attachments/assets/d06f630e-246e-436f-a713-1ed5e3691825">


## Producers
- **KafkaProducer**: Produces plain text messages to Kafka.
- **JsonKafkaProducer**: Produces JSON messages to Kafka. Each producer logs the message being sent.
## Consumers
- **KafkaConsumer**: Consumes plain text messages and logs them.
- **JsonKafkaConsumer**: Consumes JSON User objects and logs them.


## Run Kafka ( Default port number: 9092 )
- Start Zookeeper: Open a terminal and run the following command:
`bin/zookeeper-server-start.sh config/zookeeper.properties` 
- Start Kafka Server: `bin/kafka-server-start.sh config/server.properties`
- Consume message: `bin/kafka-console-consumer.sh --topic {topic-name} --from-beginning --bootstrap-server localhost:9092`

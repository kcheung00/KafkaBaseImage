# Apache Kafka Docker Image Quick Start
Quick simply docker image for testing purpose

# Summary
1. Kafka 2.8.0
2. Open JDK 11

## Build the Image
```
docker build -t kafka_quickstart:2.8.0 .
```
## Run the Image
```
docker run --name kafka-box kafka-quickstart:2.8.0
OR
docker run --name kafka-box -d kafka-quickstart:2.8.0
```
## Test Steps
1. Launch Two BASH terminal within container
   ```
   docker exec -it <Container ID> /bin/bash
   docker exec -it 2a93d33f5e11 /bin/bash
   ```
2. Navigate to KAFKA Home
   ```
   cd /usr/local/kafka
   ```
3. Create Topic
   ```
   bin/kafka-topics.sh --create --topic quickstart-events --bootstrap-server localhost:9092
   ```
4. Publish events from one terminal
   ```
   $ bin/kafka-console-producer.sh --topic quickstart-events --bootstrap-server localhost:9092
     This is my first event
     This is my second event
   ```
5. Consume events from another terminal
   ```
   bin/kafka-console-consumer.sh --topic quickstart-events --from-beginning --bootstrap-server localhost:9092
   ```
## Start the Container

## Stop the Container



## Misc Command
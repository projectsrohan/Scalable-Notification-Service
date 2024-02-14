Designing a Scalable Notification Service

````````````````````````````````Installation of KAFKA : ```````````````````````````````````````````````


``````````````````````````````````Configure Kafka:`````````````````````````````````````

Navigate to the Kafka directory (C:\kafka) and locate the config directory.
Open the server.properties file in a text editor.
Configure properties such as listeners, advertised.listeners, log.dirs, and zookeeper.connect.
listeners and advertised.listeners should specify the hostname or IP address and port where Kafka will listen for incoming connections. Example: listeners=PLAINTEXT://localhost:9092.
log.dirs specifies the directory where Kafka will store log files (e.g., C:\kafka\logs).
zookeeper.connect specifies the ZooKeeper connection string (e.g., localhost:2181).

```````````````````````````````````````````Start ZooKeeper:`````````````````````````````````````````

Kafka uses ZooKeeper for coordination. Open a Command Prompt window and navigate to the Kafka directory (C:\kafka).
Run the following command to start ZooKeeper:

bin\windows\zookeeper-server-start.bat config\zookeeper.properties

`````````````````````````````````````````Start Kafka Broker:```````````````````````````````````

Open another Command Prompt window and navigate to the Kafka directory (C:\kafka).
Run the following command to start the Kafka broker:

bin\windows\kafka-server-start.bat config\server.properties

`````````````````````````````````````````Create a Topic (Optional):``````````````````````````````

You can create a Kafka topic using the kafka-topics.bat script. For example:

bin\windows\kafka-topics.bat --create --topic my_topic --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1
```````````````````````````````````````````Verify Installation:````````````````````````````````````````

Verify that Kafka is running correctly by producing and consuming messages to and from a topic.
Use kafka-console-producer.bat to produce messages.
Use kafka-console-consumer.bat to consume messages.

``````````````````````````````````````````Kafka Cluster Configuration: ``````````````````````````````

Optimize Kafka cluster configuration parameters such as num.partitions, replication.factor, batch.size, linger.ms, and compression.type based on your workload requirements. Ensure that your Kafka cluster is appropriately sized to handle the expected message throughput.

````````````````````````````````````````Scaling Kafka:``````````````````````````````````````````````

To scale Kafka horizontally, you would repeat the setup process on additional nodes and configure them to join the Kafka cluster.
Adjust configurations such as broker.id, listeners, and advertised.listeners to reflect the new setup.

````````````````````````````````````````KAFKA ````````````````````````````````````````
Run blow in CMD and keep it running.

Run Zookeeper
Run Kafka server
Create topic
RUN Producer
RUN consumer

```````````````````````````````````````Installation & Run Nodejs : ```````````````````````````

Installation:

npm install express
npm install body-parser
npm install kafkajs
 
Run :
node index.js

``````````````````````````````````````````API ````````````````````````````````````````````````````
API : http://localhost:8080/api/send
parameter : {"message":"Message sent"}


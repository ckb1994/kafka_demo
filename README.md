Kafka Installation and setup in windows 10

1. Download binary file from apache kafka website, extract and keep in C drive ( Rename folder to kafka, without version)
2. Go inside config folder and open server.properties and change log.dir = C:/kafka/kafka-logs
3. Go inside config folder and open zookeeper.properties and change datadir=C:/kafka/zookeeper-data

Now Start the zookeeper
1. open cmd from kafka folder or navigate to kafka folder
2. run command
	.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
	
zookeeper will start at port : 2181

Now Start Kafka server
1. open cmd from kafka folder or navigate to kafka folder
2. run command
	.\bin\windows\kafka-server-start.bat .\config\server.properties
	
Now Create Topics
1. open cmd from kafka folder or navigate to kafka folder
2. run command
	.\bin\windows\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic TopicName
	
List all Topics
1. open cmd from kafka folder or navigate to kafka folder
2. run command
	.\bin\windows\kafka-topic.bat --list --zookeeper localhost:2181
	
Create Message inside Topic
1. open cmd from kafka folder or navigate to kafka folder
2. run command
	.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic TopicName
	 Here 9092 is kafka server default port
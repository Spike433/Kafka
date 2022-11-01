# Kafka



## Installations



sudo apt-get install git



sudo apt install openjdk-8-jdk



https://kafka.apache.org/downloads 2.0.0, scala 2.12



cd ~

nano ./bashrc

--> 

	export PATH=~/.local/bin:$PATH



	export PATH=/home/osboxes/Desktop/Kafka/kafka_2.12-2.0.0/bin:$PATH









osboxes@osboxes:~/Desktop/Kafka/kafka_2.12-2.0.0$ cd config/



osboxes@osboxes:~/Desktop/Kafka/kafka_2.12-2.0.0/config$ nano zookeeper.properties



dataDir=/home/osboxes/Desktop/Kafka/kafka_2.12-2.0.0/data/zookeeper



## Start Zookeeeper and Kafka



### 1. ZooKeeper

bin/zookeeper-server-start.sh config/zookeeper.properties 



### 2. Kafka

kafka-server-start.sh config/server.properties





## Start consumer



kafka-console-consumer.sh --bootstrap-server 127.0.0.1:9092 --topic first_topic



### Read consumer messages from beggining



kafka-console-producer.sh --broker-list 127.0.0.1:9092 --topic first_topic --from-beginning



### Group consumer topics



kafka-console-consumer.sh --bootstrap-server 127.0.0.1:9092 --topic first_topic 

--group my-first-application



### List consumers



kafka-consumer-groups.sh --bootstrap-server 127.0.0.1:9092 --list



### Describe groups



kafka-consumer-groups.sh --bootstrap-server 127.0.0.1:9092 --describe --group my-first-application



LAG = 0 , consumer read all data

CURRENT-OFFSET = index of read message, LOG-END = where it ends



### Reset offsets



--reset-offsets --to-earliest --execute --topic first-topic



## Start broker



kafka-console-producer.sh --broker-list 127.0.0.1:9092 --topic first_topic












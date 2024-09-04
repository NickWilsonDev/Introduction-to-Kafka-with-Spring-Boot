
Kafka info

installed using homebrew
    brew install kafka

to start up kafka

start up Zookeeper for cluster management first (since im on apple silicon -different location in file system)
    /opt/homebrew/bin/zookeeper-server-start /opt/homebrew/
etc/zookeeper/zoo.cfg


this is deprecated and KRaft is reccommended now to start with Kafka

KRaft

Generate a Cluster UUID

KAFKA_CLUSTER_ID="$(/opt/homebrew/opt/kafka/bin/kafka-storage random-uuid)"
Format Log Directories

/opt/homebrew/opt/kafka/bin/kafka-storage format -t $KAFKA_CLUSTER_ID -c /opt/homebrew/etc/kafka/kraft/server.properties


Start the Kafka Server (zookeeper is deprecated, prefer KRaft if possible)

(zookeeper mode)
    /opt/homebrew/opt/kafka/bin/kafka-server-start /opt/homebrew/etc/kafka/server.properties


(KRaft mode)
    /opt/homebrew/opt/kafka/bin/kafka-server-start /opt/homebrew/etc/kafka/kraft/server.properties



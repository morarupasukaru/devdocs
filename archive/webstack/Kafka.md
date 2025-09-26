# Kafka

[Apache Kafka](https://kafka.apache.org/) is an open-source distributed event streaming platform.
Kafka allow to decouple data streams from target systems (db, emails, logs, etc.).

*Disclaimer: this document cover not all features of Kafka*

* Concepts
  * **topic**: stream of data (without contraints) identified by a **name**
  * **partition**: topics are split in partitions
    * data in partitions are ordered (but not accross partitions!)  
    * each data within a partition has an id called **offset**
    * data are kept for a limited time (default: 1 week)
    * data are immutable in partition
    * when data is saved into a topic, the partition is choosen randomly unless a specific key is provided 
  * **broker**: synonym to server
    * broker has an ID (integer)
    * broker contains subset of topic partitions
    * connect to one broker means connecting to the whole cluster  
  * **cluster**: a kafka cluster is composed of multiple brokers
  * **topic replication**: partition are replicated above more than one broker
    * if a broker go down, another broker can still serve the data
    * replication factor (usually between 2-3; leader count has 1) is defined pro topic
    * only one broker is the leader of a given partition (receive/serve data); 
      other brokers will only synchronize the partition data (ISR: in-sync replica)
  * **producers**: write data to topics
    * producers know to which broker and partition to write to (complexity hidden by API)
    * producers implement also non-happy cases (e.g. broker down) and load-balancing logic
    * producers can choose strategy whether to receive an acknowledgment on data writes or not
      * won't wait acknowledgment (possible data loss; acks=0)
      * wait leader broker acknowledgment (limited data loss; acks=1)
      * wait leader and replicas brokers acknowledgment (no data loss; acks=all)
  * **message keys**: producers can send a key (any type) with the message (is optional)
    * if key is null, data is sent to brokers in round-robin logic 
    * if key is not null, all messages of that key will be sent to the same partition
    * typical use case: ensure order of messages of a given entity are ordered (e.g. transactions of given 
      banking account)
  * **consumers**: read data from topics (identified by name)    
    * consumers know which broker to read from
    * consumers know how to recover non-happy cases (e.g. broker down)
    * data is read in order within each partitions
  * **consumer groups**: several consumers reading in parallel
    * only one consumer can read a given partition at the same time
    * if there are more consumers than partitions, some consumers will be inactive
  * **consumer offsets**: kafka know at which partition offsets a consumer group has been reading
    * such "bookmarks" offsets are stored in a topic _consumer_offsets_
    * when a consumer in a group proceed data, it should commit the offset in the _consumer_offsets_ topic
      (done automatically but can be also customized)
    * ([offsets.retention.minutes](https://kafka.apache.org/documentation/#brokerconfigs_offsets.retention.minutes) 
      specify how long offsets are kept if consumers are missing)
  * **delivery semantics for consumers**: consumers choose one of following delivery semantics when to commit offsets: 
    * at most once: offsets are commited as soon as the message is received (if something go wrong, message is lost)
    * at least once: offsets are commited after the message is processed (usually prefered)
      * processing must be idempotent if same message is process several times 
    * exactly once
      * possible from Kafka to Kafka by using Kafka Stream API
      * possible from Kafka to external systems with idempotent consumer
  * **kafka broker discovery**: every broker knows about all brokers, topics and partitions 
    (and allocation of partitions among brokers)
    * it means that consumers/producers only have to connect to one broker to be connected to the whole cluster
    * kafka broker are therefore called "bootstrap server"
  * **zookeeper**: manages brokers together and informs Kafka about changes (new topic, broker down, etc.)
    * kafka cannot work without a running zookeeper
    * as number of servers increase, number of zookeeper server should increase as well
    * if there are several zookeeper servers, one has the lead (informs kafka) and other are followers 
      (communicate with the leader)
  * **controlling consumer liveliness**: a thread on the broker checks if consumers are alive
    (if he receives heartbeats from consumers)
  * **kafka guarantees**:
    * messages are appended to a topic-partition in the order they are sent
    * consumers read messages in the order stored in a topic-partition
    * with replicator factor of N, producers & consumers can tolerate up to N-1 broker down
      * replicator factor = 3 is good (1 broker can be down for maintenance and second unexceptelly)
      * as long as the number of partitions for a topic remains unchanged, the same key will always go the same
      partition
  * **client bidirectional compatibility**: older client can talk to newer broker or newer client can talk to older broker
    * see [article](https://www.confluent.io/blog/upgrading-apache-kafka-clients-just-got-easier)
    * always use the latest client library version if you can
  * **schema registry**
    * kafka has no data verification, bytes in input as taken as is
    * a third-party implementation of [schema registry](https://kafka.apache.org/documentation/#multitenancy-more) 
      could be added to kafka to have data contracts
    * e.g. [confluent schema registry](https://docs.confluent.io/platform/current/schema-registry/index.html)
    * with a schema registry, producer and consumer write/read data in
      [Apache Avro](https://avro.apache.org/) format
    * schema are saved in the schema registry by producers and read from consumers
* Kafka CLI
  * [start kafka](https://kafka.apache.org/documentation/#quickstart_startserver)
    * with `zookeeper-server-start` to start the ZooKeeper service
    * and `kafka-server-start.sh` to start the Kafka broker service
  * [create, update, delete, get info about topics](https://kafka.apache.org/documentation/#topicconfigs) with 
    `kafka-topics`
  * [write data into topics](https://kafka.apache.org/documentation/#quickstart_send) with `kafka-console-producer`
    * publish data on non-existing topic will create the new topic with default configuration
    * it's always good to create the topic before producing data
  * [read data from topics](https://kafka.apache.org/documentation/#quickstart_consume) with `kafka-console-consumer`
  * [managing consumer groups](https://kafka.apache.org/documentation/#basic_ops_consumer_group) with `kafka-console-consumer`
* APIs
  * [producer API](https://kafka.apache.org/documentation/#producerapi) 
    allows applications to send streams of data to topics in the Kafka cluster
    * see example in javadocs of [KafkaProducer.java](https://kafka.apache.org/36/javadoc/org/apache/kafka/clients/producer/KafkaProducer.html)
    * see [ProducerConfig.java](https://kafka.apache.org/36/javadoc/org/apache/kafka/clients/producer/ProducerConfig.html)
    and related [explanations](http://kafka.apache.org/documentation.html#producerconfigs)
      * [enable.idempotence](https://kafka.apache.org/documentation/#producerconfigs_enable.idempotence) to have
        an idempotent producer (avoid dupplicate of data)
      * [compression.type](https://kafka.apache.org/documentation/#producerconfigs_compression.type) to enable
        compression of data
      * [batch.size](https://kafka.apache.org/documentation/#producerconfigs_batch.size) and
        [linger.ms](https://kafka.apache.org/documentation/#producerconfigs_linger.ms) having impact on batch processing
  * [consumer API](https://kafka.apache.org/documentation/#consumerapi) 
    allows applications to read streams of data from topics in the Kafka cluster
    * see example in javadocs of [KafkaConsumer.java](https://kafka.apache.org/36/javadoc/org/apache/kafka/clients/consumer/KafkaConsumer.html)
    * see [ConsumerConfig.java](https://kafka.apache.org/36/javadoc/org/apache/kafka/clients/consumer/ConsumerConfig.html)
      and related [explanation](https://kafka.apache.org/documentation/#consumerconfigs)
      * [auto.offset.reset](https://kafka.apache.org/documentation/#consumerconfigs_auto.offset.reset) to specify consumer offset reset behaviour
    * consumers are polling new data from topics (polling can be configured with 
      [fetch.min.bytes](https://kafka.apache.org/documentation/#consumerconfigs_fetch.min.bytes), 
      [max.poll.records](https://kafka.apache.org/documentation/#consumerconfigs_max.poll.records),
      [max.partition.fetch.bytes](https://kafka.apache.org/documentation/#consumerconfigs_max.partition.fetch.bytes),
      [fetch.max.bytes](https://kafka.apache.org/documentation/#consumerconfigs_fetch.max.bytes);
      default values should be fine)
    * consumer offset commit strategies
      * [enable.auto.commit](https://kafka.apache.org/documentation/#consumerconfigs_enable.auto.commit) = true & synchronous processing of batches
      * [enable.auto.commit](https://kafka.apache.org/documentation/#consumerconfigs_enable.auto.commit) = false & manual commit of offsets
      * see examples of javadocs of [KafkaConsumer.java](https://kafka.apache.org/36/javadoc/org/apache/kafka/clients/consumer/KafkaConsumer.html)
  * [connect API](https://kafka.apache.org/documentation/#connectapi)
    simplify reading/writing of data but re-using working out-of-box connectors for various sources or sinks.
    * normally user won't dev custom connectors but use a pre-built connectors without writing code
    * see [kafka connect](https://kafka.apache.org/documentation.html#connect) tools to run standalone connectors
    * search available connectors at https://www.confluent.io/hub/
  * [streams API](https://kafka.apache.org/documentation/#streamsapi)
    ease data processing and transformation from input topics to output topics (within kafka)
    * see [tutorial about kafka streams](https://kafka.apache.org/34/documentation/streams/)
  * [admin API](https://kafka.apache.org/documentation/#adminapi) 
    allows managing and inspecting topics, brokers, and other Kafka objects
* Links
  * see [Intro](https://kafka.apache.org/intro) and [Quickstart](https://kafka.apache.org/quickstart) of official docs
  * see article [The Kafka API Battle: Producer vs Consumer vs Kafka Connect vs Kafka Streams vs KSQL !](https://medium.com/@stephane.maarek/the-kafka-api-battle-producer-vs-consumer-vs-kafka-connect-vs-kafka-streams-vs-ksql-ef584274c1e)
  * course [Learn Apache Kafka for Beginners](https://www.udemy.com/course/apache-kafka/)

[*Go to parent page*](README.md)

*(Page mainly written in mai 2021; links checked on 31.01.2024)*


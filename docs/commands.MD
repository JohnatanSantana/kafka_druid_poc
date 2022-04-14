```
    docker run -it --rm \
    --network docker_default \
    -e KAFKA_CFG_ZOOKEEPER_CONNECT=zookeeper-server:2181 \
    bitnami/kafka:latest kafka-topics.sh --list  --bootstrap-server kafka:9092
```

```
    docker run -it --rm \
    --network docker_default \
    -e KAFKA_CFG_ZOOKEEPER_CONNECT=zookeeper-server:2181 \
    bitnami/kafka:latest kafka-topics.sh --delete --topic purchases  --bootstrap-server kafka:9092
```


```
docker run -it --rm \
--network docker_default \
-e KAFKA_CFG_ZOOKEEPER_CONNECT=zookeeper-server:2181 \
bitnami/kafka:latest kafka-topics.sh --create --topic purchases  --bootstrap-server kafka:9092
```


```
docker run -it --rm \
--network docker_default \
-v "/home/johnatan/Documents/john/repos/kafka_druid_poc/data":"/" \
-e KAFKA_CFG_ZOOKEEPER_CONNECT=zookeeper-server:2181 \
bitnami/kafka:latest kafka-console-producer.sh  --bootstrap-server kafka:9092 --topic purchases < /wikiticker-2015-09-12-sampled.json
```

{ "name"   : "John Smith",    "sku"    : "20223",    "price"  : 23.95,    "name" : "Jane Smith",    "address" : "123 Maple Street",    "city" : "Pretendville",    "state" : "NY",    "zip"   : "12345" }
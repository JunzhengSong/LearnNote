### Java8-Java11





### Java11-Java17





### Java17-Java21

```yml
version: '3'

services:
  zookeeper:
    image: 'bitnami/zookeeper:3.8.0'
    container_name: zookeeper
    ports:
      - "2181:2181"
    environment:
      TZ: Asia/Shanghai
      ALLOW_ANONYMOUS_LOGIN: "yes"
      ZOO_SERVER_ID: 1
      ZOO_PORT_NUMBER: 2181
    network_mode: "host"

  kafka:
    image: 'bitnami/kafka:3.2.0'
    container_name: kafka
    ports:
      - "9092:9092"
    environment:
      TZ: Asia/Shanghai
      KAFKA_BROKER_ID: 1
      KAFKA_CFG_LISTENERS: PLAINTEXT://:9092
      KAFKA_CFG_ADVERTISED_LISTENERS: PLAINTEXT://150.148.47.96:9092
      KAFKA_CFG_ZOOKEEPER_CONNECT: 127.0.0.1:2181
      ALLOW_PLAINTEXT_LISTENER: "yes"
    volumes:
      - /docker/kafka/data:/bitnami/kafka/data
    depends_on:
      - zookeeper
    network_mode: "host"

  kafka-manager:
    image: sheepkiller/kafka-manager:latest
    container_name: kafka-manager
    ports:
      - "19092:19092"
    environment:
      ZK_HOSTS: 127.0.0.1:2181
      APPLICATION_SECRET: letmein
      KAFKA_MANAGER_USERNAME: thingsboard
      KAFKA_MANAGER_PASSWORD: 123456
      KM_ARGS: -Dhttp.port=19092
    depends_on:
      - kafka
    network_mode: "host"



docker run  -d --name kafka -p 9092:9092  -e 


docker run -d ALLOW_PLAINTEXT_LISTENER=yes bitnami/kafka:3.2.0 -e KAFKA_BROKER_ID=0 -e KAFKA_ZOOKEEPER_CONNECT=10.158.47.96:2181

```


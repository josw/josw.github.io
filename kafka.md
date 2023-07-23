

* 로컬에 설치
https://bsssss.tistory.com/1110



docker-compose.yml 생성
-> zookeeper 와 kafka image 를 실행한다

```
version: '2'
services:
  zookeeper:
    image: wurstmeister/zookeeper
    container_name: zookeeper
    ports:
      - "2181:2181"
  kafka:
    image: wurstmeister/kafka
    container_name: kafka
    ports:
      - "9092:9092"
    environment:
      KAFKA_ADVERTISED_HOST_NAME: 127.0.0.1
      KAFKA_ZOOKEEPER_CONNECT: zookeeper:2181
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
```





* display all consumer group of all topic 

```
root@66228381fba7:/# kafka-consumer-groups.sh --bootstrap-server localhost:9092 --all-groups --all-topics --describe

GROUP                  TOPIC           PARTITION  CURRENT-OFFSET  LOG-END-OFFSET  LAG             CONSUMER-ID                                                            HOST            CLIENT-ID
console-consumer-45625 board_topic     0          -               6               -               consumer-console-consumer-45625-1-645c6edf-0ad5-4825-8774-8b2b4c81ce47 /127.0.0.1      consumer-console-consumer-45625-1

GROUP           TOPIC           PARTITION  CURRENT-OFFSET  LOG-END-OFFSET  LAG             CONSUMER-ID                                              HOST            CLIENT-ID
jj_group        board_topic     0          6               6               0               consumer-jj_group-1-937d78a9-4818-4085-a57f-aac1d69d4c68 /172.18.0.1     consumer-jj_group-1
```


* display jj_group 


```
root@66228381fba7:/# kafka-consumer-groups.sh --bootstrap-server localhost:9092 --describe --group jj_group

GROUP           TOPIC           PARTITION  CURRENT-OFFSET  LOG-END-OFFSET  LAG             CONSUMER-ID                                              HOST            CLIENT-ID
jj_group        board_topic     0          6               6               0               consumer-jj_group-1-937d78a9-4818-4085-a57f-aac1d69d4c68 /172.18.0.1     consumer-jj_group-1
```



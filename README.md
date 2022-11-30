# kafka
### How to use ###
#git clone https://github.com/pickianeme/kafka.git
Host1
$ docker-compose -f  docker-compose-MultiPhysical01.yml up -d
$ docker-compose -f  docker-compose-MultiPhysical01.yml down

Host2
$ docker-compose -f  docker-compose-MultiPhysical02.yml up -d
$ docker-compose -f  docker-compose-MultiPhysical02.yml down

Host3
$ docker-compose -f  docker-compose-MultiPhysical03.yml up -d
$ docker-compose -f  docker-compose-MultiPhysical03.yml down

Kafdrop for Monitor Topic
docker run -d --rm -p 12000:12000 \
    -e KAFKA_BROKERCONNECT=<hostname>:port,<hostname>:port \
    -e JVM_OPTS="-Xms32M -Xmx64M" \
    -e SERVER_SERVLET_CONTEXTPATH="/" \
    obsidiandynamics/kafdrop

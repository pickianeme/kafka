## Docker Engine Install 
## Docker Compose Install
$curl -L https://github.com/docker/compose/releases/download/1.28.5/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

$sudo chmod +x /usr/local/bin/docker-compose

## Docker initial Swarm

$sudo docker swarm init --advertise-addr xx.xx.xx.xx

output

$docker swarm join --token xxxxxxx xx.xx.xx.xx:2377

Replace Docker Swarm join to Another host

Promote a worker node to the manager role

$docker node promote host2 host3

# How to use 
$git clone https://github.com/pickianeme/kafka.git

## Host1

$ /usr/local/bin/docker-compose -f docker-compose-MultiPhysical01.yml up -d

$ /usr/local/bin/docker-compose -f docker-compose-MultiPhysical01.yml down

## Host2

$ /usr/local/bin/docker-compose -f docker-compose-MultiPhysical02.yml up -d

$ /usr/local/bin/docker-compose -f docker-compose-MultiPhysical02.yml down

## Host3

$ /usr/local/bin/docker-compose -f docker-compose-MultiPhysical03.yml up -d

$ /usr/local/bin/docker-compose -f docker-compose-MultiPhysical03.yml down

## Portainer Docker Swarm Mode
Ref: https://docs.portainer.io/start/install/server/swarm/linux

$curl -L https://downloads.portainer.io/ce2-16/portainer-agent-stack.yml -o portainer-agent-stack.yml

$docker stack deploy -c portainer-agent-stack.yml portainer

$docker ps
### Login Portainer
https://localhost:9443  or https://< domain name:9443 >

## Kafdrop for Monitor Topic
docker run -d --rm -p 11000:11000 \
-e KAFKA_BROKERCONNECT=bk01.bu.ac.th:9095,bk01.bu.ac.th:9097,bk01.bu.ac.th:9099,bk02.bu.ac.th:9095,bk02.bu.ac.th:9097,bk02.bu.ac.th:9099,bk03.bu.ac.th:9095,bk03.bu.ac.th:9097,bk03.bu.ac.th:9099 \
-e SERVER_PORT=11000 \
-e JVM_OPTS="-Xms32M -Xmx64M" \
-e SERVER_SERVLET_CONTEXTPATH="/" \
obsidiandynamics/kafdrop

## How To Test Kafka
create Topick 
$opt/bitnami/kafka/bin/kafka-topics.sh --create --topic quickstart-events --replication-factor 9 --partitions 9 --bootstrap-server bk01.bu.ac.th:9095


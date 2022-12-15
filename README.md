# How to use 
$git clone https://github.com/pickianeme/kafka.git

## Docker Engine Install 
## Docker initial Swarm
$sudo docker swarm init --advertise-addr xx.xx.xx.xx

## output
$docker swarm join --token SWMTKN-1-0utdbk2wr65lgui7wzuuyr8sivlwsqaa4hlunxwnxnrvxr5ary-cfyms7xsgj74nryunna05j3om xx.xx.xx.xx:2377

Replace Docker Swarm join to Another host


## Host1

$ docker-compose -f  docker-compose-MultiPhysical01.yml up -d


$ docker-compose -f  docker-compose-MultiPhysical01.yml down

## Host2

$ docker-compose -f  docker-compose-MultiPhysical02.yml up -d

$ docker-compose -f  docker-compose-MultiPhysical02.yml down

## Host3

$ docker-compose -f  docker-compose-MultiPhysical03.yml up -d

$ docker-compose -f  docker-compose-MultiPhysical03.yml down

## Portainer Docker Swarm Mode
Ref: https://docs.portainer.io/start/install/server/swarm/linux

$curl -L https://downloads.portainer.io/ce2-16/portainer-agent-stack.yml -o portainer-agent-stack.yml

$docker stack deploy -c portainer-agent-stack.yml portainer

$docker ps
### Login Portainer
https://localhost:9443  or https://< domain name:9443 >

## Kafdrop for Monitor Topic
docker run -d --rm -p 12000:12000 \
    -e KAFKA_BROKERCONNECT=<hostname>:port,<hostname>:port \
    -e JVM_OPTS="-Xms32M -Xmx64M" \
    -e SERVER_SERVLET_CONTEXTPATH="/" \
    obsidiandynamics/kafdrop

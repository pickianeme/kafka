# kafka
kafka cluster

Kafdrop for Monitor Topic
docker run -d --rm -p 12000:12000 \
    -e KAFKA_BROKERCONNECT=<hostname>:port,<hostname>:port \
    -e JVM_OPTS="-Xms32M -Xmx64M" \
    -e SERVER_SERVLET_CONTEXTPATH="/" \
    obsidiandynamics/kafdrop

FROM rabbitmq:3-management
RUN rabbitmq-plugins enable --offline rabbitmq_mqtt
COPY docker/rabbitmq/20-mqtt.conf /etc/rabbitmq/conf.d/20-mqtt.conf
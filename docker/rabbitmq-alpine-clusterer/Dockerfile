FROM rabbitmq:3.6.9-management-alpine

ENV RABBITMQ_CLUSTERER_VERSION 1.0.3

ADD https://github.com/rabbitmq/rabbitmq-clusterer/releases/download/v${RABBITMQ_CLUSTERER_VERSION}/rabbitmq_clusterer-${RABBITMQ_CLUSTERER_VERSION}.ez /plugins/rabbitmq_clusterer-${RABBITMQ_CLUSTERER_VERSION}.ez

RUN chown -R rabbitmq:rabbitmq /plugins/rabbitmq_clusterer-${RABBITMQ_CLUSTERER_VERSION}.ez

RUN rabbitmq-plugins enable --offline rabbitmq_management rabbitmq_clusterer

COPY docker-entrypoint.sh /usr/local/bin/

RUN chmod +x /usr/local/bin/docker-entrypoint.sh

EXPOSE 15671 15672
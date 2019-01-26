#FROM debian:latest
FROM registry.access.redhat.com/rhel7-atomic

ENV APP_ROOT=/app

RUN mkdir /app
WORKDIR /app
ADD consignment-service /app/consignment-service

RUN chmod -R u+x ${APP_ROOT}/consignment-service && \
    chgrp -R 0 ${APP_ROOT} && \
    chmod -R g=u ${APP_ROOT}

EXPOSE 50051

CMD ["./consignment-service"]
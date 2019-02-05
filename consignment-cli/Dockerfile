FROM registry.access.redhat.com/rhel7-atomic
#FROM bbva/hardened-rhel

#RUN yum update -y && \
#yum install -y --setopt=tsflags=nodocs \
#iputils \
#less \
#net-tools \
#nmap-ncat \
#procps-ng \
#traceroute &&\
#	yum clean all

ENV APP_ROOT=/app

RUN mkdir -p /app
WORKDIR /app

ADD consignment.json /app/consignment.json
ADD consignment-cli /app/consignment-cli

RUN chmod -R u+x ${APP_ROOT}/consignment-cli && \
    chgrp -R 0 ${APP_ROOT} && \
    chmod -R g=u ${APP_ROOT}

EXPOSE 50052

CMD ["./consignment-cli"]

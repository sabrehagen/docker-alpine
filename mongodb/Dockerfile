FROM smebberson/alpine-consul-base:4.0.0

RUN echo "@testing http://dl-4.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories && \
    apk upgrade --update && \
    apk add mongodb@testing

EXPOSE 27017

RUN mkdir -p /var/log/mongodb /var/lib/mongodb

ADD root /

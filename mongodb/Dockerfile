FROM smebberson/alpine-consul-base:4.0.0

RUN echo "@testing http://dl-4.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories && \
    apk upgrade --update && \
    apk add mongodb@testing

EXPOSE 27017

RUN mkdir -p /var/log/mongodb /var/lib/mongodb

# assign ownership of data directories to mongodb user
RUN chown -R mongodb:mongodb /var/lib/mongodb /var/log/mongodb

ADD root /

FROM smebberson/alpine-consul-base:4.0.0

RUN echo "@testing http://dl-4.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories && \
    apk upgrade --update && \
    apk add mongodb@testing

ADD root /

# create log directory
RUN mkdir -p /var/log/mongodb

# mount host database
VOLUME /var/lib/mongodb:/var/lib/mongodb

# assign ownership of data directories to mongodb user
RUN chown -R mongodb:mongodb /var/lib/mongodb /var/log/mongodb

EXPOSE 27017

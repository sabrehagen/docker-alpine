FROM sabrehagen/alpine-consul-base

# Install redis.
RUN echo "http://dl-4.alpinelinux.org/alpine/edge/main" >> /etc/apk/repositories && \
    apk add --no-cache redis=3.2.0-r0 && \
    rm -rf /var/cache/apk/* && \
    mkdir -p /data/redis && \
    chown -R redis:redis /data/redis && \
    echo -e "include /etc/redis-local.conf\n" >> /etc/redis.conf

# Add the files.
ADD root /

# Expose the ports for redis.
EXPOSE 6379

# A volume for the redis files.
VOLUME ["/data/redis"]
FROM ghcr.io/vektor-docker/docker-base:3.3
MAINTAINER Viktor Verbitsky <vektory79@gmail.com>

ENV BASE_APTLIST="$BASE_APTLIST nginx" \
    WORKER_CONNECTIONS="" \
    WORKER_RLIMIT_NOFILE=""

COPY src/main/docker /

RUN apt-install && \
    cp --recursive --archive /usr/share/nginx/html/* /app && \
    apt-clean && \
    chmod --recursive +x /etc/my_init.d/*.sh /etc/service /usr/local/bin

EXPOSE 80

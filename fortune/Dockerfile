FROM debian:latest

RUN apt-get update \
    && apt-get install -y fortune

COPY webpage.sh /
EXPOSE 80
ENTRYPOINT ["/webpage.sh"]
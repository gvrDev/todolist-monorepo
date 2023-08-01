FROM alpine:latest

USER root

RUN apk update
RUN apk add bash
RUN apk add openrc
RUN mkdir /run/openrc && touch /run/openrc/softlevel
RUN rc-status

# NGinx
RUN apk add nginx
RUN rc-update add nginx

WORKDIR /app
COPY . .
RUN service nginx stop
RUN rm -rf /etc/nginx
RUN mv config /etc/nginx

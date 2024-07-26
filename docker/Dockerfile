FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get -y update && apt-get -y upgrade
RUN apt-get -y install gnupg curl systemctl

# install mongodb
RUN curl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg --dearmor
RUN echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-7.0.list
RUN apt-get -y update && apt-get -y install mongodb-org
RUN systemctl start mongod

# install python
RUN apt-get -y install python3-pip python3-dev build-essential
RUN mkdir /workspace
RUN mkdir /workspace/src
RUN mkdir /workspace/data

EXPOSE 27017
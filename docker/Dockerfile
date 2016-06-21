FROM 32bit/ubuntu:14.04

MAINTAINER Adailton do nascimento "dhelbegors@gmail.com"

RUN apt-get update && apt-get install -y \
    python3.4 \
    curl \
    git \
    nodejs \
    npm \
    python-pip \
    python-dev \
    python-setuptools \
    python-tk \
    python-imaging \
    python-bs4

RUN rm /usr/bin/python

RUN ln -s /usr/bin/python3.4 /usr/bin/python

RUN ln -s /usr/bin/nodejs /usr/bin/node

RUN npm -g install npm@latest && \
    npm install -g bower

ADD requirements/base.pip /
RUN pip install -r base.pip

COPY docker/scripts/runserver.sh /usr/bin/runserver
RUN  chmod +x /usr/bin/runserver

EXPOSE 8000

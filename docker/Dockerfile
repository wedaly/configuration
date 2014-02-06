# edx-platform fullstack

FROM ubuntu:12.04

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update -y && apt-get install -y build-essential software-properties-common python-software-properties curl git-core libxml2-dev libxslt1-dev python-apt python-dev python-pip
RUN git clone -b release https://github.com/edx/configuration /tmp/configuration
RUN pip install -r /tmp/configuration/requirements.txt
RUN cd /tmp/configuration/playbooks && ansible-playbook -c local ./edx_sandbox.yml -i "localhost,"

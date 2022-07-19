FROM ubuntu:latest

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update -y && apt-get install gcc python2-dev libkrb5-dev -y
RUN apt-get install python3-pip -y && pip3 install --upgrade pip
RUN pip3 install --upgrade virtualenv
RUN pip3 install pywinrm[kerberos] && pip3 install ansible && apt install -y openssh-client && apt install -y openssh-server && apt install -y sshpass

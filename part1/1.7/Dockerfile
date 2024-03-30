FROM ubuntu:22.04

RUN apt-get update

RUN apt-get -y install curl

COPY script.sh .

RUN chmod +x script.sh

CMD ./script.sh